# LastWar Alliance Bot 🚗

A Discord bot for LastWar alliances to manage train driver schedules and track loot activities.

## What Does This Bot Do?

### 🚂 Train Driver Management
- **Automatic daily reminders** - Get notified every morning about who's driving today
- **Weekly schedule** - View the full week's driver schedule at a glance
- **Flexible assignments** - Assign drivers using @mentions or custom names
- **Multi-language support** - Available in English, German, Hungarian, and Portuguese. *More languanges can be added upon request.

### 📊 Loot Activity Tracking
- **Track contributions** - Log truck loot, secret missions, and base attacks
- **Personal statistics** - View your own loot participation stats
- **Leaderboards** - See top contributors across different activity types
- **Recognition** - Highlight the most active alliance members

### ⚙️ Smart Notifications
- Automatic daily posts at your preferred time
- Shows today's driver prominently
- Displays the full weekly schedule
- Mentions today's driver for mobile notifications
- Time-aware messages (before/after train time)

## Commands

### For All Members

#### View Today's Driver
```
/alliance train view:today
```
See who's driving today with the full weekly schedule.

#### View Weekly Schedule
```
/alliance train view:week
```
Display the complete week's driver assignments with status indicators.

#### View Your Loot Stats
```
/alliance loot
```
Check your personal loot statistics:
- Total activities by type (truck, secret, base)
- Recent activity history
- Last activity timestamp

---

### For Admins (R4/R5 Only)

#### Set Weekly Schedule
```
/admin train set-week
```
Assign drivers for the entire week at once. You can:
- Mention Discord users: `@username`
- Use custom names: `*CustomName`
- Update multiple days or just one day

**Example:**
```
/admin train set-week
  monday: @JohnDoe
  tuesday: *JaneSmith
  wednesday: @UserXYZ
```

#### Set Single Day
```
/admin train set-day
```
Update the driver for just one specific day.

#### View Schedule Change Log
```
/admin train view-log
```
See who made changes to the schedule and when.

---

#### Add Loot Activity
```
/admin loot action:add
```
Log a loot activity for a member:
- **Type**: Truck Loot 🚛, Secret Mission 🕵️, or Base Attack ⚔️
- **Member**: @mention or *CustomName

**Example:**
```
/admin loot action:add type:truck member:@JohnDoe
```

#### Remove Loot Activity
```
/admin loot action:remove
```
Remove the most recent loot activity for a member.

#### View Member Stats
```
/admin loot action:view-member-stats
```
View detailed loot statistics for any member:
- Total activities by type
- Recent activity history
- Last activity date

#### View Top 10 by Type
```
/admin loot action:top-10-type
```
Display leaderboard for a specific loot type:
- 🚛 Top 10 Truck Looters
- 🕵️ Top 10 Secret Mission Contributors
- ⚔️ Top 10 Base Attackers

**Example:**
```
/admin loot action:top-10-type type:truck
```

#### View Overall Top 10
```
/admin loot action:top-10-total
```
Display overall leaderboard with breakdown:
- Total activities across all types
- Individual breakdown (truck/secret/base counts)
- Medal rankings 🥇🥈🥉

#### View Loot Audit Log
```
/admin loot action:view-log
```
See recent loot additions and removals with timestamps.

---

#### Configure Bot Settings
```
/admin config show                  - View current settings
/admin config set-time              - Change notification time
/admin config set-timezone          - Set timezone
/admin config test-notification     - Send test notification
/admin config add-admin             - Add admin role/user
/admin config remove-admin          - Remove admin role/user
```

## Daily Notifications

The bot automatically posts every day at your configured time:

### Before Train Time (13:00 weekdays / 15:00 weekends)
- 🚂 Today's driver shown prominently
- 📅 Full weekly schedule
- 🔔 Driver gets mentioned for mobile notification

### After Train Time
- ✅ "Train completed" message
- 📋 Weekly schedule with completed days checked off

## Supported Languages

The bot automatically detects the channel language and responds accordingly:
- 🇬🇧 English
- 🇩🇪 German
- 🇭🇺 Hungarian
- 🇵🇹 Portuguese

## Privacy & Data

The bot collects minimal data to function:
- Discord user IDs (for assignments and stats)
- Activity timestamps
- Schedule assignments

**We do not collect:**
- Message content
- Personal information
- IP addresses

For full details, see:
- [Privacy Policy](https://github.com/henims/LastWar-AllianceBot-Docs/blob/main/PRIVACY_POLICY.MD)
- [Terms of Service](https://github.com/henims/LastWar-AllianceBot-Docs/blob/main/TERMS_OF_SERVICE.MD)

## Getting Help

If you encounter issues or have questions:
- Contact your server admins
- Report bugs: [GitHub Issues](https://github.com/henims/LastWar-AllianceBot-Docs/issues)

## Features at a Glance

✅ **Multi-server support** - Works on multiple Discord servers
✅ **Automatic reminders** - Never forget who's driving
✅ **Flexible scheduling** - Use @mentions or custom names
✅ **Loot tracking** - Track and recognize contributions
✅ **Leaderboards** - Friendly competition and recognition
✅ **Audit logs** - Full transparency of changes
✅ **Multi-language** - Supports 4 languages
✅ **Time-aware** - Different messages before/after train time
✅ **Mobile-friendly** - Mentions work on mobile devices

---

**Made with ❤️ for LastWar alliances**
