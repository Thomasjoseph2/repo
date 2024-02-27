npm install pg

const { Client } = require('pg');

// Replace the following with your PostgreSQL database connection details
const client = new Client({
  user: 'your_username',
  host: 'your_host',
  database: 'your_database',
  password: 'your_password',
  port: 5432, // Default PostgreSQL port
});


client.connect()
   .then(() => console.log('Connected to PostgreSQL'))
   .catch(error => console.error('Error connecting to PostgreSQL', error));
   
client.query('SELECT * FROM your_table', (err, result) => {
  if (err) {
    console.error('Error executing query', err);
  } else {
    console.log('Query result:', result.rows);
  }
  client.end(); // Close the connection after executing queries
});
