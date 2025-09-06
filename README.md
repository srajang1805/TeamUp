imp instructions
Save all files in frontend in one folder,open frontpage with live server using vscode.



# Team Up

**Team Up** is a web platform that helps students and gamers find teammates based on interests, skills, and preferences. It allows users to create profiles, join or form groups, chat in real-time, and rate each other’s reliability in collaborative activities.  

Built with **HTML, CSS, JavaScript**, and powered by **Firebase** for authentication, database, and real-time features.

---

## Table of Contents
- [Features](#features)  
- [Tech Stack](#tech-stack)  
- [Matchmaking System](#matchmaking-system)  
  - [Development & Study](#development--study)  
  - [Gaming](#gaming)  
- [Group Chat](#group-chat)  
- [Authentication & Database](#authentication--database)  
- [Getting Started](#getting-started)  
- [Future Improvements](#future-improvements)

---

## Features
- **User Profiles**: Users can add personal info, interests, skills, and a profile picture.  
- **Matchmaking**: Find teammates automatically based on tags for study, development, or gaming.  
- **Group Chat**: Real-time chat with group members.  
- **Rating System**: Users can rate teammates to improve reliability tracking.  
- **Tag Management**: Users can add/remove tags for better matchmaking.  

---

## Tech Stack
- **Frontend**: HTML, CSS, JavaScript (Vanilla)  
- **Backend**: Firebase  
  - Authentication  
  - Firestore Database  
  - Realtime Database (for chat)  
  - Cloud Functions (optional, for future automation)  

---

## Matchmaking System
The platform uses **tags-based matching** to connect users with similar interests or skills.  

### Development & Study
- Users add **tags** like `Frontend`, `Backend`, `AI/ML` for development or `Math`, `Physics` for study groups.  
- The system matches users whose tag arrays **overlap** with the group’s tags.  
- Priority is given to users with more **common tags**, ensuring relevant teammates for academic or project work.  

### Gaming
- Gaming tags like `Sniper`, `Fragger`, or `Medic` help users find teammates suited to their **play style**.  
- Matching considers **role balance** in the team to enhance gameplay experience.  

The **matching algorithm**:
1. Fetches the group’s tags from Firestore.  
2. Queries users whose tags **intersect** with the group’s tags.  
3. Removes duplicates and excludes the current user.  
4. Sorts or displays users based on **common tags**.  

---

## Group Chat
- Implemented using **Firebase Realtime Database** for real-time updates.  
- Each group has a unique **chat node** in the database.  
- Messages include **sender info**, **timestamp**, and **text content**.  
- Frontend dynamically listens to changes in the chat node and updates the chat window.  
- Users can send messages instantly without page reloads.  

---

## Authentication & Database
- **Firebase Authentication** is used for login/sign-up via email and password.  
- User profiles are stored in **Firestore** with:
  - `name`  
  - `username`  
  - `email`  
  - `tags` (study, gaming, development)  
  - `reliability` rating  
  - `profile picture URL`  

- **Matchmaking, invites, and group chats** all interact with Firestore/Realtime Database to maintain **data consistency**.  
- Security rules ensure that **users can only access allowed data** (e.g., only members of a group can send/read messages).  

---

## Getting Started
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/team-up.git
