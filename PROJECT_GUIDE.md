# 🎬 YouTube Watch Party — Project & Interview Guide
**Owner:** Khushi Awasthi  
**Live URL:** [https://youtube-watch-party-0c00.onrender.com](https://youtube-watch-party-0c00.onrender.com)  
**GitHub Repository:** [https://github.com/khushiawasthi0102/youtube-watch-party](https://github.com/khushiawasthi0102/youtube-watch-party)

---

## 1. Project Overview (Yeh Project Kya Karta Hai?)
Yeh ek **Virtual Cinema Hall / Watch Party** web application hai. 
- Log apne doston ke saath ek room me judkar **YouTube video ko bilkul ek sath (synchronized)** dekh sakte hain.
- **Host (Room Banane Wala)** jab video ko Play, Pause, Seek (forward/backward) karta hai ya video change karta hai, toh sabhi doston ke screens par video usi second par apne aap sync ho jati hai.
- Sath hi live chat, reactions aur moderator roles bhi available hain.

---

## 2. Tech Stack (Kaunsi Technologies Use Hui Hain?)
- **Frontend:** React.js, Vite, React Router, CSS3
- **Backend:** Node.js, Express.js
- **Real-Time Communication:** **Socket.IO (WebSockets)**
- **Video Player API:** YouTube IFrame Player API
- **Deployment & Hosting:** Render Cloud (CI/CD via GitHub)

---

## 3. Real-Time Sync Kaise Kaam Karta Hai? (Socket.IO Architecture)
1. Normal websites HTTP requests (refresh) par chalti hain.
2. Lekin is project me **Socket.IO (WebSockets)** use hua hai, jo browser aur server ke beech ek permanent **live connection** banata hai.
3. Jab Host video ko **Play** karta hai:
   - Client event emit karta hai: `C2S.PLAY` with timestamp (e.g. `12.4s`).
   - Server room ke saare participants ko broadcast karta hai: `S2C.SYNC_PLAY`.
   - Sabhi doston ke YouTube player usi second par instant play ho jate hain bina refresh kiye.

---

## 4. Key Features
1. **Create & Join Room:** 6-character room codes aur direct invite links.
2. **Synced Playback:** Millisecond precision ke sath Play, Pause, Seek aur Video change.
3. **Roles & Permissions:** Host, Moderator, Participant, Viewer. Host permissions manage kar sakta hai.
4. **Live Chat & Reactions:** Room ke andar real-time message aur floating reactions.
5. **Room Recovery:** Server restart hone par room snapshot se recover ho sakta hai.

---

## 5. Interview Me 1-Minute Pitch (Kya Bolna Hai?)
> *"Maine ek full-stack **YouTube Watch Party** web application build kiya hai, jo multiple users ko real-time synchronized YouTube playback allow karta hai.*  
>  
> - *Iska frontend **React** me bana hai aur backend **Node.js + Express** me.*  
> - *Iska core feature hai **Real-Time Sync**, jiske liye maine **Socket.IO (WebSockets)** use kiya hai taaki Play, Pause, Seek aur Video changes bina kisi delay ke sabhi participants me sync rahein.*  
> - *Isme **Role-Based Access Control** hai (Host, Moderator, Participant) aur live chat aur emoji reactions bhi hain.*  
> - *Aur maine is project ko **Render Cloud** par CI/CD ke through live deploy kiya hua hai."*

---

## 6. How to Run Locally (VS Code Me Kaise Run Karein?)
```bash
# Terminal me likhein:
npm start

# Browser me open karein:
http://localhost:3001
```
