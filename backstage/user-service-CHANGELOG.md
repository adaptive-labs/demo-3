# Changelog - User Service

All notable changes to the User Service will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).

## [2.1.0] - 2024-12-25

### Added
- OAuth2 social login integration (Google, GitHub)
- User profile photo upload and management
- Two-factor authentication (2FA) support

### Changed
- Improved password hashing algorithm (bcrypt with higher cost)
- Updated email verification flow with better UX

### Fixed
- Session timeout not being respected in edge cases
- User search pagination offset bug

### Security
- Patched SQL injection vulnerability in user search
- Updated dependencies to address CVE-2024-12345

## [2.0.0] - 2024-11-15

### Added
- User role-based access control (RBAC)
- User groups and team management
- API key generation for service accounts

### Changed
- **BREAKING**: Renamed `user_type` field to `role`
- Database schema migration required

### Deprecated
- Legacy session tokens (will be removed in v3.0.0)

### Removed
- Support for legacy authentication API v1

## [1.5.2] - 2024-10-01

### Fixed
- Memory leak in session cleanup job
- Race condition in concurrent user updates

### Security
- Updated JWT library to fix token validation bypass

## [1.5.0] - 2024-09-01

### Added
- User activity audit logging
- Password strength meter on registration

### Changed
- Increased session timeout from 24h to 7 days

[2.1.0]: https://github.com/company/user-service/compare/v2.0.0...v2.1.0
[2.0.0]: https://github.com/company/user-service/compare/v1.5.2...v2.0.0
[1.5.2]: https://github.com/company/user-service/compare/v1.5.0...v1.5.2
[1.5.0]: https://github.com/company/user-service/releases/tag/v1.5.0
