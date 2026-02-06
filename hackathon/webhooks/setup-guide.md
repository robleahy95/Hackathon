# Webhook Setup Guide

## Option A: Make.com (Recommended - Fastest)

### Step 1: Create Account
1. Go to [make.com](https://make.com)
2. Sign up for free account
3. Verify email

### Step 2: Create New Scenario
1. Click "Create a new scenario"
2. Click the "+" button
3. Search for "Webhook"
4. Select "Webhooks" → "Custom webhook"
5. Click "Add" to create a new webhook
6. Name it "BD Assistant Lead Capture"
7. Click "Save"
8. **Copy the webhook URL** — you'll need this!

### Step 3: Add Notion Action
1. Click the "+" after the webhook
2. Search for "Notion"
3. Select "Create a Database Item"
4. Connect your Notion account (authorize Make.com)
5. Select your Leads database
6. Map fields:
   - Name → `{{1.name}}`
   - Company → `{{1.company}}`
   - Priority → `{{1.priority}}`
   - Notes → `{{1.notes}}`
   - Date Added → `{{now}}`

### Step 4: Test
1. Turn on the scenario (toggle in bottom left)
2. Click "Run once"
3. Send a test request (see below)
4. Check Notion for the new entry

### Step 5: Activate
1. Toggle scenario to "ON"
2. Set scheduling to "Immediately"

---

## Option B: Zapier

### Step 1: Create Zap
1. Go to [zapier.com](https://zapier.com)
2. Click "Create Zap"
3. Trigger: "Webhooks by Zapier" → "Catch Hook"
4. Copy the webhook URL

### Step 2: Add Action
1. Action: "Notion" → "Create Database Item"
2. Connect Notion account
3. Map fields from the webhook data

### Step 3: Test & Activate
1. Send test request
2. Turn on Zap

---

## Option C: n8n (Self-hosted)

If you have n8n running:
1. Create workflow with Webhook trigger
2. Add Notion node
3. Map fields
4. Activate workflow

---

## Notion Database Setup

Create a database with these columns:

| Column | Type | Options |
|--------|------|---------|
| Name | Title | - |
| Company | Text | - |
| Priority | Select | Hot, Warm, Cool |
| Notes | Text | - |
| Date Added | Date | - |
| Follow-up By | Date | - |
| Source | Text | - |
| Status | Select | New, Contacted, Meeting, Closed |

### Get Database ID
1. Open your Notion database
2. Click "Share" → "Copy link"
3. The URL looks like: `notion.so/workspace/DATABASE_ID?v=...`
4. Copy the DATABASE_ID part (32 characters)

---

## Testing Your Webhook

### Using curl
```bash
curl -X POST "YOUR_WEBHOOK_URL" \
  -H "Content-Type: application/json" \
  -d '{
    "name": "Test Lead",
    "company": "Test Company",
    "priority": "Hot",
    "notes": "Testing webhook integration"
  }'
```

### Using Postman
1. Create new POST request
2. URL: Your webhook URL
3. Body → raw → JSON:
```json
{
  "name": "Test Lead",
  "company": "Test Company",
  "priority": "Hot",
  "notes": "Testing webhook integration"
}
```
4. Send and check Notion

### Expected Response
- Make.com: `{"accepted": true}`
- Zapier: `{"status": "success"}`

---

## Troubleshooting

**Webhook not firing:**
- Check scenario/zap is turned ON
- Check webhook URL is correct (no typos)
- Check JSON is valid

**Notion not receiving:**
- Verify Notion connection is authorized
- Check database ID is correct
- Check field mapping matches column names

**Data not mapping:**
- Field names are case-sensitive
- Check the webhook payload structure
- Look at Make.com/Zapier logs for errors

---

## For the Hackathon

**Minimum viable setup:**
1. One webhook that creates Notion entries
2. Test it works before the event
3. Have the webhook URL saved somewhere accessible

**If time permits:**
- Add email action (SendGrid, Resend, or Gmail via Make.com)
- Add Google Sheets as backup logging
- Add Slack notification when lead is added
