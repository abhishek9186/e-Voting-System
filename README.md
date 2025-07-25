# e-Voting-System
Sign Up ->
POST /signup: Sign up a user


Login ->
POST /login: Login a user

Candidates 

Get Candidates ->
GET /candidates: Get the list of candidates

Add Candidate ->
POST /candidates: Add a new candidate (Admin only)

Update Candidate ->
PUT /candidates/:id: Update a candidate by ID (Admin only)

Delete Candidate ->
DELETE /candidates/:id: Delete a candidate by ID (Admin only)

Voting
Get Vote Count ->
GET /candidates/vote/count: Get the count of votes for each candidate

Vote for Candidate ->
POST /candidates/vote/:id: Vote for a candidate (User only)

User Profile

Get Profile->
GET /users/profile: Get user profile information

Change Password
PUT /users/profile/password: Change user password



#Only 1 Admin
In my e-voting system, I implemented a check within the user creation process to ensure that only one admin can exist at any given time. This is achieved by adding logic in the pre-save hook of the Mongoose schema.

Whenever a user is being saved with the admin role, the system first performs a query to check if an admin already exists in the database. I use the findOne() method to look for any user with the role set to admin. If such a user exists, the system throws an error, preventing the new user from being created as another admin. This ensures that no more than one admin can ever exist
