# LastWar Alliance Bot 🚗

A multi-server Discord bot for LastWar alliances to manage train driver schedules and loot tracking with automatic daily notifications.

## Features

### 🚂 Train Schedule Management
- **Daily notifications** - Automatic posts at configurable time with today's driver and weekly schedule
- **Multi-language support** - English, German, Hungarian, Portuguese, French, Czech
- **Flexible scheduling** - Support for user mentions or custom text names
- **Audit logging** - Track all schedule changes with timestamps

### 🎁 Loot Tracking
- **Activity logging** - Track truck loot, secret missions, and base attacks
- **Member statistics** - View individual member loot participation
- **Leaderboards** - See top contributors across different activity types (with caching)
- **Admin management** - Add/remove loot activities with full audit trail

### 🏢 Multi-Server Support
- Run on multiple Discord servers simultaneously
- Server-specific configurations (channels, admin roles, timezone)
- Isolated data per server (guild-aware Redis namespacing)
- Automatic cleanup of inactive guilds (30-day GDPR compliance)

### 🔒 Security Features
- **NoSQL injection protection** - Sanitized Redis key construction
- **XSS protection** - Guild name and user input sanitization
- **Prototype pollution protection** - Safe JSON parsing
- **Timing attack protection** - Constant-time comparisons
- **Rate limiting** - 10 commands/minute with Redis persistence
- **Error sanitization** - No sensitive data in error messages
- **DoS protection** - Size limits on stored data
- **Security headers** - HTTP security headers on all endpoints
- **Audit log redaction** - Sensitive data removed from logs

### ⚡ Performance Optimizations
- **Redis batching** - Pipeline and MGET for batch operations
- **Parallel operations** - Promise.allSettled for concurrent tasks
- **Multi-level caching** - Day index, leaderboards, channels, configs
- **Memory cleanup** - Automatic cache invalidation
- **N+1 prevention** - Optimized database queries

## Commands

### `/setup` (Admin only)

**Initial Configuration:**
```
/setup configure channel:#channel time:08:00 timezone:Europe/Oslo - Complete initial setup (all required)
/setup status                                                      - View current bot configuration
```

**Update Configuration (after initial setup):**
```
/setup configure channel:#new-channel - Update notification channel only
/setup configure time:09:00           - Update notification time only
/setup configure timezone:Asia/Tokyo  - Update timezone only
```

**Language Management:**
```
/setup language add language:english channel:#english-channel     - Add or update language channel
/setup language add language:german channel:#german-channel       - Add German language channel
/setup language remove language:english                           - Remove language channel
/setup language list                                              - List all configured language channels
```

### `/admin` (R4/R5 roles only)

**Train Management:**
```
/admin train set-week     - Set the weekly driver schedule (Monday-Sunday)
/admin train set-day      - Set driver for a specific day
/admin train view-log     - View audit log of schedule changes
```

**Loot Management:**
```
/admin loot action:add                   - Add loot activity for a member
/admin loot action:remove                - Remove a loot activity
/admin loot action:view-log              - View loot audit log
/admin loot action:view-member-stats     - View stats for specific member
/admin loot action:top-10-type           - Top 10 leaderboard by type
/admin loot action:top-10-total          - Top 10 overall leaderboard
```

### `/alliance` (all members)

```
/alliance train view:today  - Check who's driving today
/alliance train view:week   - Show the full weekly schedule
/alliance loot              - View your own loot statistics
```

## Quick Start

### For Server Admins (Installing the Bot)

1. **Invite the bot** using the invite URL provided by the bot owner
2. **Run `/setup configure`** in your server:
   ```
   /setup configure channel:#alliance-chat time:08:00 timezone:Europe/Oslo
   ```
3. **Add language channels** (optional):
   ```
   /setup language add language:english channel:#english-chat
   /setup language add language:german channel:#german-chat
   ```
4. **Set your train schedule**:
   ```
   /admin train set-week monday:@User1 tuesday:@User2 ...
   ```

The bot automatically detects when it's added to new servers and registers commands. No manual configuration needed!


## Multi-Server Support

The bot automatically supports multiple Discord servers with:

- **Automatic detection** - Bot detects when added to new servers
- **Dynamic configuration** - Server admins use `/setup` command to configure
- **Independent data** - Redis keys are namespaced per guild
- **Custom settings** - Different notification times, timezones per server
- **Separate channels** - Each server configures its own language channels
- **Isolated audit logs** - Each server maintains its own audit trail

### How It Works

1. **Server invites bot** using the invite URL
2. **Bot auto-registers** slash commands for that server
3. **Admin runs `/setup configure`** to set notification channel, time, and timezone
4. **Admin optionally adds** language channels with `/setup language add`
5. **Bot creates isolated** Redis namespace for that server's data

No manual configuration or server restarts needed!

## Usage Examples

### Setting Weekly Schedule (Sunday evening)

```
/admin train set-week
  monday:@User1
  tuesday:@User2
  wednesday:@User3
  thursday:@User4
  friday:@User5
  saturday:@User6
  sunday:@User7
```

**Using freetext names:**
```
/admin train set-week
  monday:*JohnDoe
  tuesday:*JaneSmith
  wednesday:@User3
  ...
```

### Adding Loot Activities

```
/admin loot add type:truck member:@User1
/admin loot add type:secret member:*CustomName
/admin loot add type:base member:@User2
```

### Viewing Statistics

```
/alliance loot-stats member:@User1
/alliance loot-leaderboard type:truck
/alliance loot-leaderboard type:all
```

### Initial Bot Setup

```
/setup configure channel:#alliance-chat time:08:00 timezone:Europe/Oslo
/setup language add language:english channel:#english-chat
/setup language add language:german channel:#german-chat
```

### Updating Configuration

```
/setup configure time:09:00
/setup configure timezone:America/New_York
/setup status
```

## Daily Notification

The bot automatically posts in configured channels at the set time with:

**Before train time (13:00 weekdays / 15:00 weekends):**
- Today's driver prominently displayed
- Full weekly schedule
- Driver mention for mobile notifications

**After train time:**
- "Train completed" message
- Weekly schedule with completed days marked

## License

MIT
