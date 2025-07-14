# ✨ Full Stack Realtime Chat App ✨

#https://deepwiki.com/sz-codes/real-time-chat/  (visit this to understand the underlying app)

Highlights:

- 🌟 Tech stack: MERN + Socket.io + TailwindCSS + Daisy UI
- 🎃 Authentication && Authorization with JWT
- 👾 Real-time messaging with Socket.io
- 🚀 Online user status
- 👌 Global state management with Zustand
- 🐞 Error handling both on the server and on the client
Eg mongodb shell commands:

# 1. Find a user by their email address
db.users.findOne({ email: "emma.thompson@example.com" })

# 2. Count the total number of messages in the database
db.messages.countDocuments()

# 3. Find all messages sent by a specific user (replace 'USER_ID_HERE' with an actual user _id)
db.messages.find({ senderId: ObjectId("USER_ID_HERE") })

# 4. Find all messages that contain an image attachment
db.messages.find({ image: { $exists: true, $ne: null } })


#Eg mongodb queries

# 1. Find all messages sent between two specific users (replace USER_ID_1 and USER_ID_2)
db.messages.find({
  $or: [
    { senderId: ObjectId("USER_ID_1"), receiverId: ObjectId("USER_ID_2") },
    { senderId: ObjectId("USER_ID_2"), receiverId: ObjectId("USER_ID_1") }
  ]
}).sort({ createdAt: 1 })

# 2. Find the 5 most recent messages globally
db.messages.find().sort({ createdAt: -1 }).limit(5)

# 3. Update a user's profile picture URL (replace USER_ID_HERE and NEW_PIC_URL)
db.users.updateOne(
  { _id: ObjectId("USER_ID_HERE") },
  { $set: { profilePic: "NEW_PIC_URL" } }
)

# 4. Find all users who have not set a profile picture (assuming default is null or empty string)
db.users.find({ profilePic: { $in: [null, ""] } })

### Setup .env file

```js
MONGODB_URI=...
PORT=5001
JWT_SECRET=...

CLOUDINARY_CLOUD_NAME=...
CLOUDINARY_API_KEY=...
CLOUDINARY_API_SECRET=...

NODE_ENV=development
```

### Build the app

```shell
npm run build
```

### Start the app

```shell
npm start
```


### DEMO IMAGES

Sign up
![WhatsApp Image 2025-04-24 at 10 29 31_f4537b38](https://github.com/user-attachments/assets/2ce0b0d6-da3a-48f9-85e8-22ae9ac39c54)
Theme Customization
![WhatsApp Image 2025-04-24 at 10 29 30_470c0788](https://github.com/user-attachments/assets/ccecae75-c2e4-43d1-ad97-1ed1d262c05a)
Chat room/users
![WhatsApp Image 2025-04-24 at 10 29 30_3a3553e4](https://github.com/user-attachments/assets/c23ff022-96fb-4929-aaf8-522bee9d85fc)
