## Shoehorn API

This file is a test.

### `upsertK8sEntityInTx`

```go
// internal/catalog/k8s_entity_service_impl.go

// ... in upsertK8sEntityInTx
	// Extract new field
	var newField *string
	if nf, ok := entityData["newField"].(string); ok && nf != "" {
		newField = &nf
	}
// ...
	query := `
		INSERT INTO catalog_entities (
			// ...
			k8s_replicas, k8s_dashboard_url, k8s_new_field,
			// ...
		) VALUES (
			// ...
			$11, $12, $13, // Add new field
			// ...
		)
		ON CONFLICT (organization_id, k8s_cluster, k8s_namespace, k8s_kind, name)
		DO UPDATE SET
			// ...
			k8s_replicas = EXCLUDED.k8s_replicas,
			k8s_dashboard_url = EXCLUDED.k8s_dashboard_url,
			k8s_new_field = EXCLUDED.k8s_new_field, // Add this
			updated_at = CURRENT_TIMESTAMP
// ...
`
// ...
	err := tx.QueryRowContext(ctx, query,
		// ...
		replicas, dashboardURL, newField, // Add newField
	).Scan(
// ...
```