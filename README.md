


Voting App
Overview
The Voting App is a comprehensive application designed to facilitate secure and efficient voting processes. It includes robust features for user authentication, candidate management, and real-time vote tracking.

Features
User Sign Up & Login:

Users can create accounts using their unique government ID (Nagrikta) and a password.
Secure login functionality.
View Candidates:

Users can view a list of all candidates participating in the vote.
Vote Once:

Each user can cast a vote for one candidate only.
Once a vote is cast, the user cannot vote again.
Live Vote Counts:

Real-time display of vote counts for each candidate.
Candidates are listed in descending order of their vote counts.
User Profile Management:

Users can view and update their profile information.
Users can change their passwords.
Admin Control:

Admins have the ability to add, update, and delete candidate details.
Admins are restricted from voting to maintain impartiality.
Technical Details
Models
User:

Fields: nagrikta, password, role (default: 'user'), isVoted (default: false)
Each user has a unique government ID (Nagrikta).
Candidate:

Fields: name, party, voteCount (default: 0), votes (array of user references)
Stores information about each candidate and their vote count.
Routes
User Authentication
Sign Up: POST /auth/signup
Login: POST /auth/login
Voting
List Candidates: GET /candidates
Vote for a Candidate: POST /candidates/vote/:candidateId
Vote Counts: GET /candidates/vote/count
User Profile
Get Profile: GET /profile
Change Password: PUT /profile/password
Admin Candidate Management
Create Candidate: POST /candidates
Update Candidate: PUT /candidates/:candidateId
Delete Candidate: DELETE /candidates/:candidateId
Security
JWT-based authentication for secure access control.
Passwords are hashed for user safety.
Setup Instructions
Clone the repository:
sh
Copy code
git clone https://github.com/yourusername/voting-app.git
Install dependencies:
sh
Copy code
cd voting-app
npm install
Set up environment variables in a .env file:
env
Copy code
MONGODB_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret_key
Start the server:
sh
Copy code
npm start
Contributions
Contributions are welcome! Please open an issue or submit a pull request for any improvements or bug fixes.
