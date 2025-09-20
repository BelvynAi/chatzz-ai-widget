# Chatzz AI Assistant Widget

A premium light-themed chat widget for restaurant/hospitality businesses that integrates with n8n webhooks for AI-powered conversations.

## Features

- 🎨 Clean light theme with teal accents
- 💬 Real-time chat interface with animated typing indicators
- 🔗 n8n webhook integration
- 📱 Responsive widget design (30% viewport width)
- 🎯 Easy embedding in WordPress/Elementor
- 🔒 Secure iframe implementation with rounded corners
- ♿ Full accessibility support
- 💾 Session persistence
- 🔐 Privacy policy integration

## Quick Start

### 1. Deploy the Application

Deploy this Next.js application to Vercel or your preferred hosting platform.

### 2. Embed in WordPress/Elementor

#### For Elementor:
1. Add an **HTML Widget** to your page
2. Insert this code:
\`\`\`html
<script src="https://YOUR-DOMAIN.vercel.app/embed.js" defer></script>
\`\`\`
3. Save and publish your page

#### For WordPress (Custom HTML Block):
1. Add a **Custom HTML** block
2. Insert the same script code
3. Update/publish your page

#### For any website:
Add this script just before the closing `</body>` tag:
\`\`\`html
<script src="https://YOUR-DOMAIN.vercel.app/embed.js" defer></script>
\`\`\`

## API Integration

The widget sends POST requests to:
\`\`\`
https://n8n.srv896614.hstgr.cloud/webhook/83c4072a-2176-4dff-bf87-4d3b4b6978f2/chat
\`\`\`

### Request Format:
\`\`\`json
{
  "chatInput": "user message here",
  "sessionId": "session_1722162000000_abc123def"
}
\`\`\`

### Response Handling:
- Plain text responses are displayed directly
- JSON responses are parsed to extract text content (e.g., `{"reply": "text"}`)
- Supports basic markdown formatting (bold, italic, code)

## Usage

Once embedded, users will see a floating teal chat button in the bottom-right corner. Clicking it opens a modal with the chat interface.

### Starter Prompts:
- "What are your opening hours?"
- "Do you have vegetarian options?"
- "Can I host a birthday party?"

### Special Commands:
- `/clear` - Clears the conversation history

## Customization

The widget uses CSS custom properties for theming:
- `--bg-primary`: White background (#FFFFFF)
- `--accent`: Teal accent color (#00A19B)
- `--text-primary`: Navy text (#1C244B)
- `--user-bubble`: Light gray user bubbles (#EAEAEA)
- `--assistant-bubble`: Very light gray assistant bubbles (#F5F5F5)

## Browser Support

- Chrome 60+
- Firefox 60+
- Safari 12+
- Edge 79+

## Security

- CSP headers configured for iframe embedding in WordPress/Elementor
- Content sanitization for assistant responses
- No API keys exposed to client
- Session data stored locally only

## Accessibility

- Full keyboard navigation support
- ARIA labels and roles
- Screen reader compatible
- Focus management
- Escape key closes modal

## Public API

The embed script exposes a global `ChatzzChat` object:

\`\`\`javascript
// Open the chat widget
window.ChatzzChat.open()

// Close the chat widget
window.ChatzzChat.close()

// Toggle the chat widget
window.ChatzzChat.toggle()
