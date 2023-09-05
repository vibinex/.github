# Alokit Innovations
Alokit Innovations Private Limited is an Information Technology company based in India.
The goal of this company is to maximize the effeciency, longetivity and impact of software teams.
The founders of Alokit Innovations firmly believe that the only way to build long-lasting entities is to make them self-sufficient. So Alokit Innovations is a for-profit firm.

### FOSS Pledge
As an organization, we pledge to:
1. Openly credit and talk about the FOSS that we use in our organization and acknowledge the value we derive from them wherever appropriate.
2. Encourage our developers and technical staff to create and contribute to FOSS and participate in FOSS communities and activities.
3. Try and provide financial and other support to the FOSS projects that are valuable to our organization.
4. Publish notes on our aforementioned FOSS related activities at least annually.

## Vibinex Code Review
This is our flagship product ([vibinex.com](https://vibinex.com)). It modifies the UX for code-hosting websites like GitHub and Bitbucket to make it easier to perform high-quality code reviews.
There are three key repositories of this product:
1. [User-side repository processing service (Rust)](https://github.com/Alokit-Innovations/dev-profiler)
2. [Server for backend and website (NextJS)](https://github.com/Alokit-Innovations/team-monitor-website)
3. [Browser Extension](https://github.com/Alokit-Innovations/chrome-extension)

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://github.com/Alokit-Innovations/.github/assets/7858932/def425db-07f1-4a6b-90ce-9c3cf0bb4aae">
  <source media="(prefers-color-scheme: light)" srcset="https://github.com/Alokit-Innovations/.github/assets/7858932/358856bc-03b9-4c2e-aa55-a88d9ce4130b">
  <img alt="Vibinex core repo" src="https://github.com/Alokit-Innovations/.github/assets/7858932/358856bc-03b9-4c2e-aa55-a88d9ce4130b">
</picture>

### Privacy-first
We take privacy extremely seriously. The purpose of the Rust service is to keep the user's data (code, events, config, server logs, etc.) in the user's infrastructure.
Only non-reproducible encrypted/hashed metadata is shared with Vibinex's servers. 

This project follows a dual-backend architecture to ensure privacy while serving data-enabled features. Here is the architectural diagram (over-simplified for high-level understanding):

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://github.com/Alokit-Innovations/.github/assets/7858932/493b3052-b462-4bb8-a9cd-ffa8e1018960">
  <source media="(prefers-color-scheme: light)" srcset="https://github.com/Alokit-Innovations/.github/assets/7858932/d5a97883-64ef-498f-b97a-318b6675ac87">
  <img alt="2-backend architecture" src="https://github.com/Alokit-Innovations/.github/assets/7858932/d5a97883-64ef-498f-b97a-318b6675ac87">
</picture>

### Constraints
1. Sensitive and private information can only be accessed by the user-side service and cannot be shared with any other part of application
2. Only metadata or other processed output from the data (which cannot be used to reproduce any sensitive information) can be shared with the central server.
3. Any data stored in the central server must be hashed (preferably) or encrypted (with the private key on user-side).
4. Any changes in the schema of the data shared outside of the user-side service must go through a user-consent process.
5. The user-side service must not be verey resource intensive (exact thresholds TBD).

## Alokit Mentorship Platform
This website ([alokit.in](https://alokit.in)) facilitates running temporary employment engagements (like internships, contract work, consultancy etc.). It acts as a trusted third party for 
- Project management (with JIRA-like epics, stories and tasks)
- Payments (Deposits at the start of the project and compensation at the end based on completion, with an added feature of buy-ins)
- NDA and other legal

This project is hosted on Firebase. 
1. Firestore is the primary database
2. Backend is a NodeJS (ExpressJS) server hosted on Firebase Functions
3. Frontend is written in ReactJS and statically hosted using Firebase Hosting

All the code is in a [single GitHub Repository](https://github.com/Alokit-Innovations/mentorship-platform), which is a single Firebase project organized in two folders (`functions` and `view` for the backend and the frontend respectively).
