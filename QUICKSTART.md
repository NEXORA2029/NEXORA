# Nexora SAR - Quick Start Guide

## 🚀 Getting Started in 5 Minutes

### Prerequisites Check
Before starting, ensure you have:
- ✅ Node.js installed (v16+)
- ✅ npm or yarn package manager
- ✅ Modern web browser (Chrome, Firefox, Edge)
- ✅ Terminal/Command Prompt access

### Installation Steps

#### 1. Install Dependencies

Open your terminal in the project root directory and run:

```bash
# Install backend dependencies
npm install

# Navigate to client folder
cd client

# Install frontend dependencies
npm install

# Return to root
cd ..
```

#### 2. Create Environment File

Copy the example environment file:

```bash
# Windows
copy .env.example .env

# Mac/Linux
cp .env.example .env
```

The default settings work fine for local development!

#### 3. Start the Application

**Recommended: Run both servers together**

```bash
npm run dev
```

This will start:
- Backend API on http://localhost:5000
- Frontend app on http://localhost:3000

**Alternative: Run separately**

Terminal 1 (Backend):
```bash
npm run server
```

Terminal 2 (Frontend):
```bash
cd client
npm run dev
```

#### 4. Open in Browser

Navigate to: **http://localhost:3000**

You should see the Nexora SAR dashboard!

---

## 🎮 Quick Demo Walkthrough

### Step 1: Create a Mission
1. On the dashboard, click one of the "Quick Start Templates" buttons
2. Or manually enter:
   - Mission Name: "Test Search"
   - Latitude: 40.7589
   - Longitude: -73.9851
   - Search Radius: 2 km
3. Click "🚀 Deploy Drone System"

### Step 2: Run the Scan
1. You'll be taken to the Mission Control view
2. Click "🚀 Start Scanning"
3. Watch the map as:
   - Grid cells turn yellow (currently scanning)
   - Grid cells turn green (scanned)
   - Red markers appear (detections found)

### Step 3: Review Detections
1. Check the right panel for detection cards
2. Each shows:
   - Confidence score (percentage)
   - Detection type (thermal/thermal+RGB)
   - Precise coordinates
   - Timestamp
3. Click markers on the map for more details

---

## 🔧 Troubleshooting

### Port Already in Use

If you see "Port 3000 is already in use":

```bash
# Windows - Kill process on port 3000
netstat -ano | findstr :3000
taskkill /PID <PID> /F

# Mac/Linux
lsof -ti:3000 | xargs kill -9
```

### Dependencies Not Installing

Try clearing npm cache:

```bash
npm cache clean --force
npm install
```

### Map Not Loading

1. Check your internet connection (map tiles load from OpenStreetMap)
2. Try refreshing the page
3. Check browser console for errors (F12)

### Backend Not Responding

1. Verify backend is running: http://localhost:5000/api/health
2. Should return: `{"status":"ok","message":"Nexora SAR System API is running"}`
3. Check terminal for error messages

---

## 📱 Browser Compatibility

Tested and working on:
- ✅ Chrome 90+
- ✅ Firefox 88+
- ✅ Edge 90+
- ✅ Safari 14+

---

## 🎯 Demo Tips for Presentations

### For Judges/Viewers

1. **Start with Dashboard** - Show all 6 features clearly
2. **Explain Architecture** - Point to the workflow diagram
3. **Create Mission Live** - Use a recognizable location
4. **Run Scan** - Let them see real-time progress
5. **Show Detection** - Explain confidence scoring
6. **Emphasize Ethics** - Mention disclaimers and limitations

### Talking Points

- "This reduces search time from hours to minutes"
- "Uses affordable commercial drones, not expensive custom hardware"
- "AI-assisted, not fully autonomous - humans verify all detections"
- "Designed for the critical first 24 hours"
- "Can be deployed by small police or rescue units"

### Common Questions & Answers

**Q: How accurate is the detection?**
A: Our prototype simulates 65-95% confidence scores. In production, this would use trained models on real thermal data. All detections require human verification.

**Q: What drones does this work with?**
A: Any commercial drone with thermal camera capability (e.g., DJI Mavic 2 Enterprise, Autel EVO II Dual). No custom hardware needed.

**Q: How long does a typical search take?**
A: A 2km radius area with 200m grid cells takes approximately 15-20 minutes to scan completely (in simulation).

**Q: Can this work at night?**
A: Yes! Thermal imaging is actually MORE effective at night when temperature contrast is higher.

**Q: What about privacy concerns?**
A: This is designed specifically for SAR operations with proper authorization. Data is not stored permanently and is only used for active rescue missions.

---

## 📊 Performance Metrics

### System Capabilities (Prototype)
- Search radius: 0.5 - 5 km
- Grid cell size: 200m x 200m
- Scan speed: ~1.5 seconds per cell (simulated)
- Detection rate: ~15% (for demo purposes)
- Confidence range: 55% - 95%

### Real-World Projections
- Actual drone speed: 5-10 m/s
- Flight time: 20-30 minutes per battery
- Coverage: ~1-2 km² per flight
- Detection accuracy: 70-90% (with trained models)

---

## 🎨 Customization

### Changing Colors

Edit `client/src/index.css` and modify CSS variables:

```css
:root {
  --color-primary: hsl(210, 100%, 55%);  /* Change primary color */
  --color-secondary: hsl(280, 85%, 60%); /* Change secondary color */
}
```

### Adjusting Scan Speed

Edit `client/src/components/MissionControl.jsx`:

```javascript
// Line ~50 - Change interval time (milliseconds)
scanIntervalRef.current = setInterval(async () => {
  // ... scanning logic
}, 1500); // Change this value (1500 = 1.5 seconds)
```

### Modifying Grid Cell Size

Edit `server/index.js`:

```javascript
// Line ~95 - Change cell size
const cellSizeKm = 0.2; // Change this (0.2 = 200 meters)
```

---

## 🔐 Security Notes

### For Production Deployment

This prototype does NOT include:
- ❌ Authentication/Authorization
- ❌ Input validation/sanitization
- ❌ Rate limiting
- ❌ HTTPS encryption
- ❌ Database security

**Do NOT deploy this to production without adding proper security measures!**

---

## 📈 Next Steps

After running the demo:

1. **Explore the Code** - Well-commented and organized
2. **Customize Features** - Add your own enhancements
3. **Test Different Scenarios** - Try various locations and radii
4. **Prepare Presentation** - Practice the demo flow
5. **Document Learnings** - Note what worked well

---

## 💡 Tips for Success

### Before the Hackathon
- ✅ Test the entire flow multiple times
- ✅ Prepare backup demo video (in case of technical issues)
- ✅ Have screenshots ready
- ✅ Know your talking points
- ✅ Understand the code architecture

### During Presentation
- ✅ Start with the problem (missing persons statistics)
- ✅ Show the solution (live demo)
- ✅ Explain the technology (AI + drones)
- ✅ Address limitations honestly
- ✅ Emphasize real-world applicability

### Handling Questions
- ✅ Be honest about prototype limitations
- ✅ Explain future enhancement plans
- ✅ Reference similar real-world systems
- ✅ Emphasize humanitarian focus
- ✅ Show enthusiasm for the technology

---

## 🎓 Learning Resources

### Technologies Used
- [React Documentation](https://react.dev)
- [Leaflet Mapping](https://leafletjs.com)
- [Express.js Guide](https://expressjs.com)
- [Node.js Docs](https://nodejs.org)

### SAR Technology
- [Thermal Imaging in SAR](https://www.flir.com/discover/public-safety/search-and-rescue/)
- [Drone SAR Operations](https://www.dji.com/newsroom/news/drones-in-search-and-rescue)

---

**Ready to save lives with technology! 🚁💙**
