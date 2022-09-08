# Backend - Giskard programming problem


This is the backend of the Millenium falcon App

## Install the package
Run 
```
pip install -r requirements.txt
pip install -e .
```

## CLI
After Installing the CLI will work with the following command
```
give-me-the-odds <path to millennium-falcon.json> <path to empire.json path>
Example -
give-me-the-odds millenium_falcon/tests/examples/example3/millennium-falcon.json millenium_falcon/tests/examples/example3/empire.json
```

## APP
To run the app run the below command 
```
python3 millenium_falcon/api.py
```
The app can be accessed at `http://localhost:5001/`
By default the Falcon Inputs will be taken from the `/inputs` folder in the package root. Following files are expected in the folder 
- millennium-falcon.json
- universe.db

The empire.json file should be upload in the frontend and the corresponding success probability will be shown on the screen


## Algorithm

DFS(source planet) (O(n^n))
    if planet is destination
        add the current sequence of path from source to destination as a valid path
    for each planet in neighbour(source planet)
        mark planet as visited and dont visit it again (also if no fuel is left add a stay on the planet enroute)
        DFS(planet)
        backtrack by unmarking the planet

source planet -> The planet where the falcon starts the journey
DFS(source planet) -> Generate all valid paths (along with refuelling stay) from source to destianation 
for each path O(p*n)
    avoid bounty hunters -> by staying at the previous planet (until the countdown permits one additional day of stay)
Finally, find the success percentage corresponding to the minimum number of encounters in any path 



## Authors

- [@Gideon-12](https://github.com/Gideon-12)
