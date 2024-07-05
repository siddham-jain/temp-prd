# PRD-Student GitHub Performance Tracker

**Problem Statement:** Currently in our dev coursework, we are graded based on GitHub commits and awarded attendance for that particular day, as well as bonus marks according to the assigned task, which we have to commit.

This process includes:
-> Respective TAs collecting the link to student's github repo
-> Manually going to each student's repo and checking the commits
-> Grading based on the commits of the repo

Drawbacks of this approach are:
-> Currently there are 191 students, and checking repo of each and every individual is a cumbersome task(in future there will be more than 1000 students)
-> If they are grading on the basis of commits student can make fake commits for the sake of marks
-> this will hinder the learning process of student and increase the workload on respective TAs

## Project Overview(MVP)

`1. What?`
We are planning to build a tool that will grade students automatically by analyzing their commits in their GitHub repo.

`2. How?`
-> Fetch data of students' commit using github's api
-> Give the data to llm's api(maybe OpenAI, not finalized yet) which will give the score based on the progress of the given task by the teacher
-> GPT will generate score and justification for the given score 
-> Leaderboard will be based on the score generated by GPT

## Detailed Requirements

1. Commit Evaluation System:
	-  `what is a bad commit?` - It has context dependent definition which includes 
		-> Any commit not relevant to the subject
		-> Evaluation on the progress of daily task(By task, I refer to what instructor has taught during the class)
	- Get commit data and define a daily task to GPT
	- Let GPT do its magic(return score and justification for the given score)
2. Teacher's View:
	- A dashboard to input daily tasks
	- View of under performing students(daily and overall)
	- Access to individual student progress
	- Ability to edit the marks awarded
3. Student's View:
	- Date, Task, Score, Comment (justification for given score/feedback)
	- Personal performance history
	- View of daily and aggregated leaderboard
	- Input field for link of github repo
4. Data collection and processing:
	- Github data collection for each student daily
	- Integration with llm's API for commit evaluation
	- Score calculation and storage
5. Technical Requirements:
	- Frontend: React JS
	- Backend: ExpressJS
	- Database: MongoDB
	- APIs: GitHub and OpenAI
	- Hosting: AWS
## Future Scope

- GPT can hallucinate. We will implement RAG to tackle this
- Implement subject-wise filtering(like right now we have OS and personal project path in dev course)
- Implement more detailed analysis.

