const express = require('express');
const connectDB = require('./config/db');
const taskRoutes = require('./routes/tasks');
const dotenv = require('dotenv');

dotenv.config();

const app = express();

connectDB();

app.use(express.json());
app.use('/api/tasks', taskRoutes);

const PORT = process.env.PORT || 5000;
app.listen(PORT, () => {
    console.log(`Server running on port ${PORT}`);
});
