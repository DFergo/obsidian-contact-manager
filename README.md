# ContactManager - Obsidian Plugin

A comprehensive contact management system for Obsidian that helps organize professional contacts, companies, trade unions, and organizations with interactive contact cards and automatic relationship detection.

## ✨ Features

- **📄 Interactive Contact Cards**: Visual cards with photos, roles, and contact details
- **🔗 Automatic Relationship Detection**: Links between people and their organizations
- **🏢 Multiple Contact Types**: People, Companies, Trade Unions, Organizations
- **🎨 Color-Coded Relationships**: Visual indicators for different relationship types
- **🔍 Advanced Search & Filter**: Real-time filtering across all contact properties
- **📁 Flexible Organization**: Customizable folder structure and templates
- **🌍 Multilingual Support**: Instructions in English, Spanish, French, and Japanese

## 🚀 Quick Start

1. **Install the plugin** and activate it in Community Plugins
2. **Configure contact types** in settings - choose which types you need
3. **Set up folders** where each contact type will be stored
4. **Create your first contact** using the ribbon icon (👥) or command palette

## 🔧 Plugin Components

### Contact Manager View
Main interface accessible via ribbon icon (👥) with:
- **Browse**: All contacts organized by type tabs
- **Search**: Real-time filtering across all properties
- **Sort**: Alphabetically or by organization
- **Create**: Quick contact creation button

### Contact Cards in Notes
Interactive cards that automatically appear in contact files showing:
- Profile photos and basic information
- Color-coded relationships (Management-green, Union-red, Organization-purple)
- Clickable navigation between related contacts
- Organization logos as overlays on member cards

## 📋 Contact Properties

### People
- `type: People` (required)
- `coverImage`: Profile photo
- `role`: Job title
- `email`, `phone`: Contact information
- `company`: [[CompanyName]] - creates relationship link
- `tradeUnion`: [[UnionName]] - creates relationship link
- `collections`: ["TradeUnion"] - required for union member detection

### Companies/Organizations/Trade Unions
- `type`: Company/Organization/TradeUnion (required)
- `coverImage`: Logo displayed on card and member overlays
- `website`: Clickable URL link
- `contactInfo`: General contact details
- `management`: [["Person1", "Person2"]] - shows management section
- `people`: [["Person1", "Person2"]] - shows members section

### Universal Properties
- `description`: Displayed in card description
- `tags`: Obsidian tags for organization
- `lastUpdated`: Leave empty for automatic tracking

## 🔗 How Relationships Work

The plugin automatically detects relationships:
- Set person's `company` property → Shows them in company's management/people
- Add someone to `management` array → Shows management section
- Set `tradeUnion` + collections: ["TradeUnion"] → Shows union membership

## ⚙️ Configuration

### Contact Types
Enable only the contact types you need. Disabled types won't appear in:
- Creation dialogs
- Sorting options
- Contact Manager tabs

### Folder Structure
Configure multiple folders for each contact type. The plugin searches all specified folders.

### Templates
Customize the YAML frontmatter structure for each contact type with template variables:
- `{{title}}`: Replaced with contact name
- `{{date}}`: Replaced with current date

## 🎯 Best Practices

- Use consistent file naming conventions
- Add profile photos with `coverImage` property
- Use `[[WikiLinks]]` format for all contact references
- Disable unused contact types to simplify interface
- Fill key properties for full functionality

## 📦 Installation

### Manual Installation
1. Download the latest release files: `main.js`, `manifest.json`, `styles.css`
2. Create folder: `VaultFolder/.obsidian/plugins/contact-manager/`
3. Copy the files to this folder
4. Reload Obsidian and enable the plugin

## 🤝 Contributing

Contributions are welcome! Please feel free to submit issues and enhancement requests.

## 📄 License

MIT License - see LICENSE file for details.

## 🔧 Development

Built with TypeScript for Obsidian API. Key files:
- `src/contact-types.ts`: Interfaces and templates
- `src/contacts-view.ts`: Main plugin interface
- `src/contact-card-view.ts`: Card rendering
- `src/link-resolver.ts`: YAML parsing and relationships

---

**Version**: 1.0.0
**Compatibility**: Obsidian 0.15.0+
**Author**: Malicia