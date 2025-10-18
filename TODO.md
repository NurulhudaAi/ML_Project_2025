0) Ground rules
	•	main = clean, runnable, submission-ready. Don’t commit directly.
	•	Do all work on feature branches: feat/<task>, bugfixes on fix/<issue>, chores on chore/<thing>.
	•	Never push data, model artifacts, or outputs. Keep them local only.

# Clone
git clone https://github.com/NurulhudaAi/ML_Project_2025.git
cd ML_Project_2025

# Get main
git fetch -p
git switch main
git pull

# Local-only folders (stay out of Git)
mkdir -p data export src/artifacts
touch data/.gitkeep export/.gitkeep src/artifacts/.gitkeep

# Put your datasets locally (do NOT push):
# data/high_salary.csv
# data/high_salary.live.csv




:: Step for open Jupyter Notebook ::

docker compose up
# then open http://localhost:8888
# project is mounted at /home/jovyan/work

git switch main
git pull                 # get latest main

git switch -c feat/<your-task>    # e.g., feat/eda, feat/modeling, feat/preprocess

git add .
git commit -m "feat: <what you did>"
git push -u origin feat/<your-task>

git fetch origin
git merge origin/main
git push

7) Branch naming & commit messages
	•	Branches: feat/<work>, fix/<issue>, chore/<task>
	•	Commits: start with a type
	•	feat: new work
	•	fix: bug fix
	•	chore: infra/docs/config
	•	refactor:, docs:, test:


ML_Project_2025/│
├── data/
├── model/          
│    ├── train_and_cv.py
│    ├── predict_live.py
│    └── artifacts/
├── export/
├── docker-compose.yml
└── README.md