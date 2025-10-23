# Privacy Policy

**Last Updated:** October 23, 2025

## 1. Introduction

This Privacy Policy describes how LastWar Alliance Bot ("the Bot", "we", "us") collects, uses, and protects your information when you use our Discord bot service.

## 2. Information We Collect

### 2.1 Automatically Collected Information

When you use the Bot, we collect:
- **Discord User IDs**: To identify users for administrative actions and statistics
- **Discord Guild (Server) IDs**: To separate data between different servers
- **Discord Channel IDs**: For notification delivery
- **Timestamps**: When actions are performed

### 2.2 User-Provided Information

Users and administrators may provide:
- **Train driver assignments**: User mentions or freetext names
- **Loot activity records**: Type and timestamp of activities
- **Configuration settings**: Notification times, timezones, admin roles

### 2.3 Information We DO NOT Collect

We do not collect:
- Message content outside of Bot commands
- Private/direct messages
- User profile information beyond IDs
- IP addresses or device information
- Email addresses or personal contact information

## 3. How We Use Your Information

We use collected information to:
- **Provide Bot functionality**: Schedule management, notifications, statistics
- **Multi-guild operation**: Keep server data separate and isolated
- **Audit logging**: Track administrative actions for accountability
- **Service improvement**: Monitor Bot performance and reliability

## 4. Data Storage and Security

### 4.1 Storage Location

Data is stored in:
- **Application Server**: Hosted on Railway in EU West region (Amsterdam, Netherlands)
- **Redis Database**: Hosted on Upstash (secure cloud Redis provider)
- **Encrypted in transit**: All connections use TLS/SSL encryption

### 4.2 Data Retention

- **Active Data**: Retained while the Bot is in your server
- **Audit Logs**: Kept for 30 days, with sensitive data redacted for privacy protection
- **Statistics**: Retained indefinitely for leaderboard purposes
- **Automatic Deletion**: When the Bot leaves a server, all guild-specific data is automatically deleted after 30 days

### 4.3 Security Measures

We implement comprehensive security measures to protect your data:

**Infrastructure Security:**
- Secure database connections (TLS/SSL encryption)
- Guild-namespaced data isolation (servers cannot access each other's data)
- Security headers on all HTTP endpoints
- Regular security updates and monitoring

**Input Validation & Sanitization:**
- NoSQL injection protection in database queries
- XSS (Cross-Site Scripting) vulnerability protection
- Pattern validation for all user inputs
- Size limits to prevent Denial-of-Service attacks (CWE-770)

**Access Control & Privacy:**
- Rate limiting (10 commands per minute) to prevent abuse
- Fail-closed rate limiter mode for enhanced security
- Timing attack protection for user validation
- Sensitive data redaction in audit logs and error messages
- Custom admin role support for granular access control

**Cryptographic Security:**
- Cryptographically secure random number generation (crypto.randomBytes)
- Prototype pollution protection in JSON parsing
- Secure session and token handling

## 5. Data Sharing and Third Parties

### 5.1 We Do Not Sell Data

We do not sell, rent, or trade your information to third parties.

### 5.2 Service Providers

We use the following services:
- **Discord API**: For bot functionality (governed by Discord's Privacy Policy)
- **Railway**: For application hosting (governed by Railway's Privacy Policy)
- **Upstash Redis**: For data storage (governed by Upstash's Privacy Policy)
- **GitHub**: For code hosting and issue tracking

### 5.3 Legal Requirements

We may disclose information if required by law or to:
- Comply with legal obligations
- Protect our rights and safety
- Prevent fraud or abuse

## 6. Your Rights and Choices

You have the right to:

### 6.1 Access Your Data
- Use `/alliance loot` to view your own statistics
- Server admins can view all server data via Bot commands

### 6.2 Delete Your Data
- Use `/admin loot remove` to remove specific activities
- Remove the Bot from your server to schedule data deletion
- Contact us for manual data deletion requests

### 6.3 Opt-Out
- Remove the Bot from your server at any time
- Server admins can disable specific features

## 7. Children's Privacy

The Bot does not knowingly collect information from users under 13 years of age. Discord's Terms of Service require users to be at least 13 years old.

## 8. International Data Transfers

Data may be stored and processed in:
- **Europe (EU West)**: Railway application hosting (Amsterdam, Netherlands), Upstash Redis
- **United States**: Discord API

By using the Bot, you consent to these transfers.

## 9. Changes to This Privacy Policy

We may update this Privacy Policy from time to time. Changes will be:
- Documented with a "Last Updated" date
- Announced in the Bot's GitHub repository
- Effective immediately upon posting

## 10. Data Breach Notification

In the event of a data breach affecting user information, we will:
- Investigate and contain the breach
- Notify affected users via Discord or GitHub
- Report to relevant authorities if required by law

## 11. Contact Us

For privacy-related questions, concerns, or data deletion requests:

- **GitHub Issues**: [LastWar-AllianceBot Issues](https://github.com/henims/LastWar-AllianceBot-Docs/issues)
- **GitHub Repository**: [LastWar-AllianceBot](https://github.com/henims/LastWar-AllianceBot-Docs)

## 12. Consent

By using the Bot, you consent to this Privacy Policy and our collection and use of information as described herein.

---

**Summary**: We collect minimal data (Discord IDs, timestamps, user-provided activity records) to provide Bot functionality. We do not sell data. You can delete your data by removing the Bot or contacting us.
