## Plantuml

```uml
@startuml
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/master/C4_Context.puml
' If your environment blocks remote includes, see note below for local includes.

title System Context - Online Shop

Person(customer, "Customer", "Buys products online.")
System(shop, "Online Shop", "Allows customers to browse and purchase products.")
System_Ext(payment, "Payment Provider", "Processes card payments.")
System_Ext(email, "Email Service", "Sends order confirmations.")

Rel(customer, shop, "Browses and purchases")
Rel(shop, payment, "Charges credit cards", "HTTPS")
Rel(shop, email, "Sends emails", "SMTP/API")

@enduml
```

### Mermaid

flowchart LR
  customer[Customer]

  subgraph shop[Online Shop (System)]
    web[Web App\n(React)]
    api[API\n(Node.js)]
    db[(Database)\n(PostgreSQL)]
  end

  payment[Payment Provider\n(External)]
  email[Email Service\n(External)]

  customer -->|Uses HTTPS| web
  web -->|Calls HTTPS/JSON| api
  api -->|Reads/Writes| db
  api -->|Charges card| payment
  api -->|Sends confirmation| email
