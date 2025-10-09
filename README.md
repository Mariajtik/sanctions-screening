# 🛡️ Sanctions Screening System

**Professional compliance tool for screening entities against OFAC, EU, and UN sanctions lists**

[![Live Demo](https://img.shields.io/badge/demo-live-success)](https://mariajtik.github.io/sanctions-screening/)
[![GitHub](https://img.shields.io/badge/github-mariajtik-blue)](https://github.com/mariajtik/sanctions-screening)
[![License](https://img.shields.io/badge/license-MIT-green)](LICENSE)

🔗 **[View Live Demo](https://mariajtik.github.io/sanctions-screening/)**

---

## 📋 Overview

A full-stack sanctions screening application designed for financial institutions, fintechs, and crypto exchanges to ensure compliance with international sanctions regulations.

### Key Features

✅ **CSV Upload** - Batch screening of multiple entities  
✅ **Fuzzy Matching** - Detects typos, aliases, and name variations using Levenshtein distance algorithm  
✅ **Three-tier Status System** - CLEAR / FLAGGED / UNDER REVIEW  
✅ **Export Results** - Download screening reports for audit trails  
✅ **Real-time Processing** - Instant screening with confidence scores  
✅ **Professional UI** - Modern, responsive design with Tailwind CSS  

---

## 🎯 Use Cases

- **Banking** - KYC/AML compliance during customer onboarding
- **Fintech** - Verify users before account creation
- **Crypto Exchanges** - Screen wallet addresses and users
- **Payment Processors** - Block transactions to sanctioned entities
- **Compliance Teams** - Manual review workflow for edge cases

---

## 🏗️ Tech Stack

### Frontend
- **React 18** - Component-based UI
- **Tailwind CSS** - Modern styling
- **Lucide Icons** - Professional iconography

### Backend (Expandable)
- **Node.js + Express** - REST API
- **PostgreSQL** - Database with full-text search
- **Fuzzy Matching** - Custom Levenshtein algorithm

### Data Sources
- OFAC (Office of Foreign Assets Control)
- EU Sanctions List
- UN Security Council Sanctions

---

## 🚀 Quick Start

### Option 1: View Live Demo
Simply visit: **[https://mariajtik.github.io/sanctions-screening/](https://mariajtik.github.io/sanctions-screening/)**

### Option 2: Run Locally

```bash
# Clone repository
git clone https://github.com/mariajtik/sanctions-screening.git

# Navigate to folder
cd sanctions-screening

# Open in browser
open index.html
```

---

## 💡 How It Works

### 1. Upload Entities
Prepare a CSV file with the following format:
```csv
Name,Address,Country
John Smith,123 Main St,USA
Vladimir Putin,Moscow Kremlin,Russia
```

### 2. Fuzzy Matching Algorithm
The system uses **Levenshtein distance** to calculate similarity:

```javascript
similarity = ((maxLength - distance) / maxLength) * 100
```

### 3. Classification
- **≥ 95% match** → **FLAGGED** (immediate block)
- **75-94% match** → **UNDER REVIEW** (manual review required)
- **< 75% match** → **CLEAR** (approved)

### 4. Export Results
Download a CSV report with:
- Entity details
- Match status
- Confidence score
- Matched sanction details (if any)

---

## 📊 Sample Data

The system includes sample OFAC sanctions:

| Name | Country | Program | Date Added |
|------|---------|---------|------------|
| Vladimir Putin | Russia | UKRAINE-EO13661 | 2014-03-06 |
| Kim Jong Un | North Korea | DPRK | 2016-07-06 |
| Nicolás Maduro | Venezuela | VENEZUELA | 2018-05-21 |
| Bashar Al-Assad | Syria | SYRIA | 2011-05-18 |

---

## 🔐 Compliance & Security

### Regulatory Compliance
- ✅ **OFAC Compliant** - Screens against U.S. Treasury sanctions
- ✅ **EU Sanctions** - Compatible with European Union lists
- ✅ **UN Sanctions** - Supports United Nations Security Council data
- ✅ **Audit Trail** - Complete history of all screenings

### Security Features
- Client-side processing (no data sent to external servers)
- No localStorage usage (session-only data)
- HTTPS-ready for production deployment

---

## 🛠️ Architecture

```
┌─────────────────┐
│   React App     │ ← User interface (CSV upload, results display)
│   (Frontend)    │
└────────┬────────┘
         │
         ↓
┌─────────────────┐
│ Fuzzy Matching  │ ← Levenshtein algorithm
│    Algorithm    │
└────────┬────────┘
         │
         ↓
┌─────────────────┐
│ Sanctions List  │ ← OFAC/EU/UN data (hardcoded for demo)
│   (In-Memory)   │
└─────────────────┘
```

### Future Backend Integration
```
React → Express API → PostgreSQL
                   ↓
              OFAC API (auto-update)
```

---

## 📈 Roadmap

### Phase 1 (Completed) ✅
- [x] CSV upload functionality
- [x] Fuzzy matching algorithm
- [x] Status classification system
- [x] Export to CSV
- [x] Professional UI/UX

### Phase 2 (Planned)
- [ ] Backend API (Node.js + PostgreSQL)
- [ ] Real-time OFAC API integration
- [ ] User authentication
- [ ] Manual review dashboard
- [ ] Email/Slack notifications

### Phase 3 (Future)
- [ ] Machine learning for improved matching
- [ ] Blockchain address screening
- [ ] Mobile app (React Native)
- [ ] Multi-language support

---

## 🧪 Testing

### Sample Test Cases

**Test 1: Exact Match**
```
Input: "Vladimir Putin"
Expected: FLAGGED (100% confidence)
```

**Test 2: Typo Detection**
```
Input: "Vlademir Putin" (typo: 'e' instead of 'i')
Expected: UNDER REVIEW (92% confidence)
```

**Test 3: Clean Entity**
```
Input: "John Smith"
Expected: CLEAR (0% confidence)
```

---

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/amazing-feature`)
3. **Commit** your changes (`git commit -m 'Add amazing feature'`)
4. **Push** to the branch (`git push origin feature/amazing-feature`)
5. **Open** a Pull Request

### Development Guidelines
- Follow existing code style
- Add comments for complex logic
- Test all features before submitting
- Update README if adding new features

---

## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

---

## 👤 Author

**Maria Baptista**
- GitHub: [@mariajtik](https://github.com/mariajtik)

---

## 🙏 Acknowledgments

- **OFAC** - U.S. Department of the Treasury sanctions data
- **Anthropic Claude** - AI assistance in development
- **React** - UI framework
- **Tailwind CSS** - Styling framework

---

## 📞 Support

For questions or issues:
- Open an [Issue](https://github.com/mariajtik/sanctions-screening/issues)
- Contact: [All here](https://github.com/Mariajtik/Mariajtik)

---

## 🌟 Show Your Support

If this project helped you, please consider:
- ⭐ Starring the repository
- 🐛 Reporting bugs
- 💡 Suggesting new features
- 📢 Sharing with others

---

<div align="center">
  <strong>Built with ❤️ by Maria Baptista</strong>
  <br><br>
  <a href="https://mariajtik.github.io/sanctions-screening/">🚀 View Live Demo</a>
</div>
