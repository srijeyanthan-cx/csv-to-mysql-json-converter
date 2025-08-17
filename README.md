# 🚀 CSV to MySQL JSON Converter

A powerful, generic web-based tool that converts CSV data into MySQL INSERT statements with JSON payloads. Perfect for migrating data to modern database schemas that store structured data as JSON.
![Uploading image.png…]()


## ✨ Features

- **🔄 Generic Converter**: Works with any CSV structure and any MySQL table schema
- **🎯 Smart Field Mapping**: Map CSV columns to custom JSON keys with automatic type detection
- **📊 Data Type Support**: String, Number, Boolean, Array with intelligent conversion
- **🔍 JSON Parsing**: Parse JSON strings within CSV fields automatically  
- **⚙️ Flexible Configuration**: Custom table names, column names, and ID mapping
- **📝 Newline Handling**: Multiple options for text fields with line breaks
- **👁️ Preview Mode**: See your JSON structure before conversion
- **📋 Easy Copy**: One-click copy to clipboard functionality
- **🎨 Modern UI**: Clean, responsive interface with step-by-step workflow

## 🎯 Use Cases

- **Database Migration**: Convert legacy CSV exports to modern JSON-based schemas
- **Data Import**: Bulk import structured data into applications using JSON storage
- **API Data Prep**: Prepare CSV data for APIs that expect JSON payloads
- **Schema Transformation**: Convert relational data to document-based storage

## 🚀 Quick Start

1. **Clone the repository**:
   ```bash
   git clone https://github.com/yourusername/csv-to-mysql-json-converter.git
   cd csv-to-mysql-json-converter
   ```

2. **Open the tool**:
   - Simply open `index.html` in your web browser
   - No server setup required - it's a pure client-side application

3. **Convert your data**:
   - Paste your CSV data
   - Analyze the structure
   - Configure your database settings
   - Map fields to JSON keys
   - Generate MySQL statements

## 📖 How to Use

### Step 1: Input CSV Data
```csv
id,name,email,age,active
1,John Doe,john@example.com,30,true
2,Jane Smith,jane@example.com,25,false
```

### Step 2: Configure Database
- **Table Name**: `users`
- **ID Column**: `id` 
- **JSON Column**: `profile_data`

### Step 3: Map Fields
- `name` → `fullName` (String)
- `email` → `emailAddress` (String)  
- `age` → `age` (Number)
- `active` → `isActive` (Boolean)

### Step 4: Generate Output
```sql
INSERT INTO users (id, profile_data) VALUES (1, '{
  "fullName": "John Doe",
  "emailAddress": "john@example.com",
  "age": 30,
  "isActive": true
}');
```

## 🛠️ Advanced Features

### Data Type Conversion
- **String**: Regular text fields with newline handling options
- **Number**: Automatic parsing of numeric values
- **Boolean**: Converts "true/false", "True/False", "1/0" to proper booleans
- **Array**: Splits comma-separated values into arrays

### JSON Parsing
Enable "Parse as JSON" for CSV fields containing JSON strings:
```csv
metadata
"{""category"": ""electronics"", ""tags"": [""phone"", ""mobile""]}"
```
Becomes:
```json
{
  "metadata": {
    "category": "electronics", 
    "tags": ["phone", "mobile"]
  }
}
```

### Newline Handling
For text fields with line breaks, choose from:
- **Escape as \\n**: Standard JSON escaping
- **Convert to &lt;br&gt;**: HTML line breaks
- **Split into array**: Each line becomes an array element

## 🔧 Technical Details

- **Pure HTML/CSS/JavaScript**: No frameworks or dependencies except PapaParse
- **CSV Parsing**: Uses PapaParse library for robust CSV handling
- **Browser Compatibility**: Works in all modern browsers
- **No Server Required**: Completely client-side processing
- **Privacy Focused**: No data leaves your browser

## 📁 Project Structure

```
csv-to-mysql-json-converter/
├── index.html              # Main application file
├── README.md              # This file
└── LICENSE                # License file
```

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/amazing-feature`)
3. **Commit** your changes (`git commit -m 'Add amazing feature'`)
4. **Push** to the branch (`git push origin feature/amazing-feature`)
5. **Open** a Pull Request

### Ideas for Contributions
- Add support for more data types (Date, UUID, etc.)
- Implement batch processing for large files
- Add export options (SQL file download)
- Create preset configurations for common use cases
- Add validation for JSON syntax

## 🐛 Bug Reports

Found a bug? Please create an issue with:
- **Description** of the problem
- **Steps to reproduce**
- **Expected behavior**
- **Sample CSV data** (if applicable)

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **PapaParse**: For excellent CSV parsing capabilities
- **Community**: For feature requests and feedback

## 📊 Example Use Cases

### E-commerce Product Import
Convert product catalogs from CSV to JSON-based product tables:
```sql
INSERT INTO products (id, details) VALUES (1, '{
  "name": "Wireless Headphones",
  "price": 99.99,
  "categories": ["electronics", "audio"],
  "inStock": true
}');
```

### User Profile Migration
Transform user data for modern authentication systems:
```sql  
INSERT INTO user_profiles (user_id, profile_data) VALUES (1, '{
  "personalInfo": {
    "firstName": "John",
    "lastName": "Doe"
  },
  "preferences": ["email_notifications", "dark_mode"],
  "accountStatus": "active"
}');
```

### Configuration Data
Convert application settings to JSON configuration tables:
```sql
INSERT INTO app_config (id, config_json) VALUES (1, '{
  "features": {
    "darkMode": true,
    "notifications": false
  },
  "limits": {
    "maxUsers": 1000,
    "maxFiles": 500
  }
}');
```

---

⭐ **Star this repository if it helped you!** ⭐

Made with ❤️ for developers dealing with data migration and CSV conversion challenges.
