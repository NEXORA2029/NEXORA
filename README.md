# Nexora SAR - AI-Assisted Drone-Based Search & Rescue System

![Nexora SAR](https://img.shields.io/badge/Status-Prototype-blue)
![License](https://img.shields.io/badge/License-MIT-green)
![Hackathon](https://img.shields.io/badge/Purpose-Hackathon-orange)

## 🚁 Project Overview

Nexora SAR is a **working prototype** demonstrating how AI-assisted drone technology can revolutionize search-and-rescue operations for missing persons. This system is designed for **everyday SAR operations** during the critical first 24 hours, particularly in semi-urban and nearby open areas.

### Key Innovation
Combining **low-cost commercial drones** with **AI-powered thermal and RGB analysis** to locate missing people faster than traditional manual search methods.

---

## ✨ Core Features

### 1. 🗺️ Smart Search Zone Mapping
- Interactive map interface for defining search areas
- Last-seen location input with customizable search radius
- Visual priority zone highlighting
- Intelligent search area optimization

### 2. 📡 Automated Grid-Based Scanning
- Systematic grid pattern generation
- Simulated drone flight path visualization
- Real-time scanning progress tracking
- Complete area coverage guarantee

### 3. 🔥 Thermal + RGB Human Detection
- Dual-spectrum imaging analysis
- AI-powered object detection
- Bounding box visualization
- Sample thermal image processing

### 4. 🎯 AI Confidence Scoring
- Probabilistic detection scoring (0-100%)
- Confidence level categorization (Low/Medium/High)
- Transparent methodology explanation
- Based on heat signature + shape analysis

### 5. 📍 Location Pinning & Alert Dashboard
- Real-time detection markers on map
- Coordinate precision to 6 decimal places
- Thumbnail previews and metadata
- Comprehensive alert panel

### 6. 💰 Low-Cost, Rapid Deployment
- Commercial off-the-shelf (COTS) drone compatible
- No custom hardware required
- Minimal setup time
- Accessible to small rescue units

---

## 🏗️ System Architecture

```
┌─────────────┐    ┌──────────────┐    ┌─────────────┐    ┌─────────────┐    ┌──────────────┐
│   Input     │ -> │   Generate   │ -> │    Drone    │ -> │     AI      │ -> │    Alert     │
│  Location   │    │     Grid     │    │    Scan     │    │  Analysis   │    │     Team     │
└─────────────┘    └──────────────┘    └─────────────┘    └─────────────┘    └──────────────┘
```

**Workflow:**
1. **Input Location** - Last seen coordinates
2. **Generate Grid** - Systematic search pattern creation
3. **Drone Scan** - Thermal + RGB image capture
4. **AI Analysis** - Human detection with confidence scoring
5. **Alert Team** - Location pinning with metadata

---

## 🛠️ Technology Stack

### Frontend
- **React 18** - Modern UI framework
- **Vite** - Fast build tool
- **React-Leaflet** - Interactive mapping
- **Axios** - API communication
- **Framer Motion** - Smooth animations
- **CSS3** - Custom design system with glassmorphism

### Backend
- **Node.js** - Runtime environment
- **Express** - Web framework
- **RESTful API** - Clean architecture
- **In-memory storage** - Prototype data handling

### Design
- **Premium Dark Theme** - Modern aesthetics
- **Glassmorphism** - Elevated UI elements
- **Gradient Accents** - Visual hierarchy
- **Micro-animations** - Enhanced UX
- **Responsive Design** - Mobile-friendly

---

## 📦 Installation & Setup

### Prerequisites
- Node.js (v16 or higher)
- npm or yarn

### Step 1: Install Dependencies

```bash
# Install root dependencies
npm install

# Install client dependencies
cd client
npm install
cd ..
```

### Step 2: Environment Configuration

Create a `.env` file in the root directory:

```env
PORT=5000
NODE_ENV=development
```

### Step 3: Run the Application

**Option A: Run both frontend and backend together**
```bash
npm run dev
```

**Option B: Run separately**

Terminal 1 (Backend):
```bash
npm run server
```

Terminal 2 (Frontend):
```bash
npm run client
```

### Access the Application
- **Frontend**: http://localhost:3000
- **Backend API**: http://localhost:5000
- **Health Check**: http://localhost:5000/api/health

---

## 🎮 Usage Guide

### Creating a Mission

1. **Navigate to Dashboard** - View system features and architecture
2. **Choose Quick Start** - Select a preset location or enter custom coordinates
3. **Configure Mission**:
   - Enter mission name
   - Set latitude and longitude
   - Adjust search radius (0.5 - 5 km)
4. **Deploy** - Click "Deploy Drone System"

### Running a Scan

1. **Mission Control** - Automatically opens after mission creation
2. **Start Scanning** - Click "Start Scanning" button
3. **Monitor Progress**:
   - Watch grid cells turn green as they're scanned
   - View real-time progress percentage
   - Observe detections appear on map
4. **Review Detections**:
   - Check confidence scores
   - View precise coordinates
   - Read detection methodology

### Understanding Detections

**Confidence Levels:**
- 🟢 **High (80-100%)** - Strong thermal + RGB match
- 🟡 **Medium (65-79%)** - Moderate confidence
- 🔴 **Low (55-64%)** - Requires verification

**Detection Basis:**
- Heat signature intensity
- Shape similarity to human form
- Environmental context
- Movement patterns (when available)

---

## 🎯 API Endpoints

### Missions

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/health` | Health check |
| POST | `/api/missions` | Create new mission |
| GET | `/api/missions` | Get all missions |
| GET | `/api/missions/:id` | Get specific mission |
| POST | `/api/missions/:id/start` | Start mission scanning |
| POST | `/api/missions/:id/scan-cell` | Scan individual grid cell |
| GET | `/api/missions/:id/detections` | Get mission detections |

### Detections

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/detections` | Get all detections |
| GET | `/api/detections/image/:id` | Get detection image |

---

## 📊 Project Structure

```
nexora/
├── client/                 # Frontend React application
│   ├── src/
│   │   ├── components/    # React components
│   │   │   ├── Header.jsx
│   │   │   ├── Dashboard.jsx
│   │   │   └── MissionControl.jsx
│   │   ├── App.jsx        # Main app component
│   │   ├── main.jsx       # Entry point
│   │   └── index.css      # Design system
│   ├── index.html
│   ├── package.json
│   └── vite.config.js
├── server/                # Backend Node.js application
│   └── index.js          # Express server
├── package.json          # Root package.json
├── .env.example          # Environment template
└── README.md            # This file
```

---

## 🎨 Design Philosophy

### Visual Excellence
- **Premium aesthetics** over basic MVP
- **Vibrant color palette** with HSL-based gradients
- **Modern typography** (Inter + Space Grotesk)
- **Glassmorphism effects** for depth
- **Smooth animations** for engagement

### User Experience
- **Intuitive navigation** with clear visual hierarchy
- **Real-time feedback** during operations
- **Responsive design** for all devices
- **Accessible controls** with proper labeling

### Technical Clarity
- **Transparent AI methodology** - No black box claims
- **Probabilistic scoring** - Honest about limitations
- **Educational focus** - Explains how it works
- **Demo-ready** - Optimized for presentations

---

## ⚠️ Important Disclaimers

### Prototype Status
This is a **proof-of-concept demonstration** for hackathon purposes, not a production-ready system.

### AI Accuracy
- Detection is **AI-assisted**, not fully autonomous
- Confidence scores are **probabilistic estimates**
- All detections **require human verification**
- System does **not claim 100% accuracy**

### Intended Use
- **Educational and humanitarian demonstration only**
- Not for military or surveillance applications
- Does not store or track personal data beyond demo
- Uses publicly available SAR methodologies

### Ethical Considerations
- Respects privacy and data protection
- Transparent about capabilities and limitations
- Designed for rescue operations, not surveillance
- Emphasizes human oversight in decision-making

---

## 🚀 Future Enhancements

### Technical Improvements
- [ ] Real drone integration via SDK
- [ ] Actual thermal camera feed processing
- [ ] Advanced ML models (YOLO, Faster R-CNN)
- [ ] Multi-drone swarm coordination
- [ ] Weather condition analysis
- [ ] Terrain difficulty mapping

### Feature Additions
- [ ] Mobile app for field teams
- [ ] SMS/Email alert notifications
- [ ] Historical mission database
- [ ] Export reports (PDF/CSV)
- [ ] Team collaboration tools
- [ ] Voice command integration

### Scalability
- [ ] Database integration (PostgreSQL/MongoDB)
- [ ] Cloud deployment (AWS/Azure)
- [ ] Load balancing for multiple missions
- [ ] Real-time WebSocket updates
- [ ] Authentication and authorization
- [ ] Multi-organization support

---

## 🤝 Contributing

This is a hackathon prototype, but suggestions are welcome!

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add AmazingFeature'`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

---

## 👥 Team

**Nexora Team** - Hackathon Participants

- Built with ❤️ for search-and-rescue operations
- Powered by AI and modern web technologies
- Designed to save lives during critical hours

---

## 🙏 Acknowledgments

- OpenStreetMap for mapping tiles
- Leaflet.js for mapping library
- React community for excellent documentation
- Search-and-rescue professionals for inspiration
- Hackathon organizers for the opportunity

---

## 📞 Support

For questions or issues:
- Open an issue on GitHub
- Contact the team during hackathon presentation
- Review the inline code documentation

---

## 🎯 Evaluation Criteria Addressed

### How does this reduce search time?
- **Systematic grid coverage** eliminates random searching
- **Parallel scanning** covers large areas quickly
- **AI-assisted detection** reduces manual monitoring burden
- **Real-time alerts** enable immediate response

### How is this better than manual drone monitoring?
- **Automated flight paths** ensure complete coverage
- **AI analysis** processes imagery faster than humans
- **Confidence scoring** prioritizes high-probability targets
- **Persistent tracking** maintains all detection data

### Can small rescue units realistically use this?
- **Low-cost COTS drones** - No expensive custom hardware
- **Simple web interface** - Minimal training required
- **Rapid deployment** - Minutes, not hours
- **Clear workflow** - Easy to understand and operate

### Is the workflow understandable within 2-3 minutes?
- **Visual dashboard** shows all features at a glance
- **Interactive demo** allows hands-on exploration
- **Clear architecture diagram** explains the process
- **Real-time visualization** demonstrates capabilities

---

**Built for the future of search-and-rescue operations. 🚁**
