# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added
- New experimental feature for AI-powered documentation generation
- Support for multi-language documentation

### Changed
- Updated sidebar navigation to use new component architecture

## [2.14.3] - 2024-12-21

### Fixed
- Currency conversion rounding errors in payment processor
- Race condition in session management
- Memory leak in WebSocket connection handler

### Security
- Updated dependencies to patch CVE-2024-12345
- Implemented rate limiting on authentication endpoints

## [2.14.2] - 2024-12-15

### Fixed
- Search index corruption on concurrent updates
- Incorrect pagination in user list endpoint

## [2.14.0] - 2024-12-10

### Added
- New payment method validation for international cards
- Support for webhook retry mechanism
- Dashboard widget for real-time metrics

### Changed
- Improved error messages for API validation failures
- Refactored authentication middleware for better performance
- Updated UI components to use new design system

### Deprecated
- Legacy CSV export endpoint (use /api/v2/export instead)
- Old authentication flow (migrate to OAuth 2.0)

## [2.13.5] - 2024-12-01

### Fixed
- Critical bug in transaction rollback logic
- Timezone handling in scheduled reports

### Security
- Fixed SQL injection vulnerability in search endpoint
- Patched XSS vulnerability in user profile rendering

## [2.13.0] - 2024-11-20

### Added
- Kubernetes deployment support with Helm charts
- Prometheus metrics endpoint
- Health check improvements for load balancers
- New REST API endpoints for batch operations

### Changed
- Migrated from MongoDB to PostgreSQL
- Updated Node.js from v16 to v20
- Refactored frontend to use Svelte 5

### Removed
- Deprecated GraphQL endpoint (sunset date: 2024-11-01)
- Legacy admin panel (replaced with new dashboard)

## [2.12.0] - 2024-11-05

### Added
- Support for custom themes
- Dark mode throughout the application
- Export functionality for all report types

### Changed
- Improved search performance by 3x
- Updated branding and logo
- Simplified onboarding flow

## [2.11.2] - 2024-10-28

### Fixed
- Email notification delivery issues
- Cache invalidation bug causing stale data
- Mobile responsive layout on iOS Safari

## [2.11.0] - 2024-10-15

### Added
- Two-factor authentication support
- API key management interface
- Audit log for security events

### Changed
- Enhanced permission model with role-based access control
- Improved documentation with interactive examples

## [2.10.0] - 2024-10-01

### Added
- Integration with Slack for notifications
- GitHub OAuth authentication
- Automated backup system

### Deprecated
- Basic authentication (will be removed in v3.0.0)

## [2.9.5] - 2024-09-20

### Fixed
- Performance degradation under high load
- Memory optimization in background workers
- File upload size limit enforcement

### Security
- Updated all dependencies to latest secure versions
- Implemented Content Security Policy headers

## [2.9.0] - 2024-09-10

### Added
- WebSocket support for real-time updates
- GraphQL subscriptions
- Advanced filtering in search

### Changed
- Redesigned settings page
- Improved mobile app performance
- Updated terms of service

## [2.8.0] - 2024-08-25

### Added
- Multi-tenant support
- Custom domain configuration
- SSO integration with SAML 2.0

### Changed
- Database schema optimization
- API rate limiting improvements

## [1.0.0] - 2024-01-15

### Added
- Initial release
- Core authentication and authorization
- Basic CRUD operations for all entities
- REST API v1
- Web dashboard
- User management
- Role-based permissions
- Email notifications
- Activity logging
