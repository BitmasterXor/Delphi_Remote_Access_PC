# Delphi Remote Access (Delphi 7 and Delphi XE5)

**Features:**
- Remote Access using the **RFB algorithm** (captures only screen changes).
- **Data Compression** for efficient communication.
- **File Sharing** capabilities.
- **Chat** feature for communication.
- **Form Inheritance** to access multiple machines simultaneously in separate windows.

---

## 📽️ Demo Video
[Watch on YouTube](https://www.youtube.com/watch?v=bq_2-Dxu2R0)

---

## 🛠️ Setup Instructions

### Delphi 7
1. Open Delphi and go to the **"Component"** menu.
2. Click **"Install Packages..."**.
3. Click **"Add"**.
4. Navigate to the `Bin` folder where Delphi is installed:  
   `C:\Program Files (x86)\Borland\Delphi7\Bin`.
5. Select **`dclsockets70.bpl`** and click **Open**.
6. Restart Delphi and reopen the project.

### Delphi XE5
1. Open Delphi and go to the **"Component"** menu.
2. Click **"Install Packages..."**.
3. Click **"Add"**.
4. Navigate to the `Bin` folder where Delphi is installed:  
   `C:\Program Files (x86)\Embarcadero\RAD Studio\12.0\Bin`.
5. Select **`dclsockets190.bpl`** and click **Open**.
6. Restart Delphi and reopen the project.

---

## 📁 Units in the Project

- **`zLibEx.pas`**  
  Used for data compression.  
  *(Copy the `zLib` folder into your project directory.)*

- **`StreamManager.pas`**  
  Handles screen capture and comparison.

- **`SndKeys32.pas`**  
  Simulates keyboard input.

---

## ⚙️ How It Works

1. The **Client** connects to the **Server**.  
   - The first socket initializes and connects others (for image transfer, file operations, or remote keyboard input).  
   - It transfers messages, mouse position, and clicks.

2. The **Server requests an initial screen capture.**  
   - The Client captures the screen as an 8-bit **Bitmap** to reduce size.  
   - The image is compressed with **zLib** and sent to the Server.  
   - The image is saved in memory.

3. Subsequent requests:  
   - The Client compares the new capture with the previous one.  
   - Only differences are sent, compressed to minimize data size.

---

## 📝 License
This source code is distributed for free.  
**Author:** Maickonn Richard  
**Contact:** senjaxus@gmail.com  

> **Disclaimer:**  
> The author is not responsible for any misuse of this software.
