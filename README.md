SLE-4: Architecture Decision Record — A* vs BFS for the 8-Puzzle

Course: 02AML204 – Introduction to Artificial Intelligence (SEM-VI) Student: Pranjal Vijay Mane PRN: 25UAM096 | Division: B Institute: DKTE Society's Textile and Engineering Institute, Ichalkaranji

Overview

This repository holds my work for the Introduction to AI self-learning evaluations (SLE). SLE-4 documents one key design choice from the earlier work as an Architecture Decision Record (ADR), which is later defended in a short viva.

Decision Summary
Item	Details
Problem	Solve the 8-puzzle (find the move sequence from a start state to the goal)
Decision	Use A* search with Manhattan distance instead of Breadth-First Search (BFS)
Why	A* uses a heuristic to guide the search, so it expands far fewer nodes than BFS while still finding an optimal solution
Heuristic	Manhattan distance (admissible and consistent, so A* stays optimal)
Trade-off	Slightly more complex code and per-node overhead (priority queue + heuristic) in exchange for much lower node expansion and memory use

The full reasoning (context, options considered, consequences) is in the ADR document in this repo.

SLE Progress
SLE	Work	Status
SLE-1	Rule-based Python chatbot (agent.py)	Done
SLE-2	BFS vs A* on the 8-puzzle, profiled with py-spy and a node counter	Done
SLE-3	C4 architecture model (draw.io)	Done
SLE-4	ADR + viva	This submission
Benchmark Setup (from SLE-2)
Start state: 1 2 3 / 5 0 6 / 4 7 8 (list form: 1,2,3,5,0,6,4,7,8)
Goal state: 1 2 3 / 4 5 6 / 7 8 0
Method: each algorithm run 5 times, results averaged
Tools: py-spy for profiling, a node counter for nodes expanded
Results
Metric	BFS	A* (Manhattan)
Nodes expanded	fill in	fill in
Avg. time (s)	fill in	fill in
Solution length	fill in	fill in
Repository Contents
.
├── README.md                # This file
├── ADR.pdf                  # Architecture Decision Record (2-3 pages)
├── bfs.py                   # BFS solver
├── astar.py                 # A* solver (Manhattan distance)
└── diagrams/                # C4 model (draw.io export)

Adjust file names to match what is actually in your repo.

How to Run
bash
git clone https://github.com/manepranjal07-design/SLE-AI.git
cd SLE-AI
python astar.py
python bfs.py

Requires Python 3.x. To profile: py-spy record -o profile.svg -- python astar.py

Tools Used
Python
py-spy (profiling)
draw.io (C4 diagrams)
GitHub Copilot / AI tools (contributions logged in the contribution log)
Links
Repository: https://github.com/manepranjal07-design/SLE-AI.git
