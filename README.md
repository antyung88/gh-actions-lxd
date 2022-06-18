# gh-actions-lxd

Setup & Run LXD/LXC in GitHub Actions

# Usage

```
      - uses: actions/checkout@v3
      - uses: antyung88/gh-actions-lxd@v2.1
        with:
          channel: latest/stable
```

Available Channels:
```
  latest/stable:    5.2-79c3c3b   2022-06-01 (23155) 106MB -
  latest/candidate: 5.2-e1612c0   2022-06-16 (23193) 106MB -
  latest/beta:      ↑
  latest/edge:      git-ab477c5   2022-06-18 (23211) 106MB -
  5.2/stable:       5.2-79c3c3b   2022-06-01 (23155) 106MB -
  5.2/candidate:    5.2-79c3c3b   2022-05-27 (23155) 106MB -
  5.2/beta:         ↑
  5.2/edge:         ↑
  5.1/stable:       5.1-1f6f485   2022-05-12 (23037)  84MB -
  5.1/candidate:    5.1-1c377db   2022-05-17 (23101)  84MB -
  5.1/beta:         ↑
  5.1/edge:         ↑
  5.0/stable:       5.0.0-b0287c1 2022-04-20 (22923)  83MB -
  5.0/candidate:    5.0.0-b0287c1 2022-04-19 (22923)  83MB -
  5.0/beta:         ↑
  5.0/edge:         ↑
  4.24/stable:      4.24-c92c0b2  2022-04-01 (22754)  82MB -
  4.24/candidate:   4.24-c92c0b2  2022-04-01 (22754)  82MB -
  4.24/beta:        ↑
  4.24/edge:        ↑
  4.0/stable:       4.0.9-8e2046b 2022-03-26 (22753)  71MB -
  4.0/candidate:    4.0.9-8e2046b 2022-03-24 (22753)  71MB -
  4.0/beta:         ↑
  4.0/edge:         git-407205d   2022-03-31 (22797)  73MB -
  3.0/stable:       3.0.4         2019-10-10 (11348)  55MB -
  3.0/candidate:    3.0.4         2019-10-10 (11348)  55MB -
  3.0/beta:         ↑
  3.0/edge:         git-81b81b9   2019-10-10 (11362)  55MB -
```

# Usage Example 

```
./github/workflow/actions.yml
```
```
Name: Setup & Run LXD/LXC in GitHub Actions

on:
  push:

jobs:
  Build:
    name: Setup LXD
    runs-on: ubuntu-latest  ## Available on Ubuntu only ##
    steps:
    
      - uses: actions/checkout@v3
      - uses: antyung88/gh-actions-lxd@v2.1
        with:
          channel: latest/stable
          
      - name: Launch instance
        run: |
          lxc launch ubuntu:20.04 test1
          lxc launch ubuntu 18.04 test2
          lxc launch ubuntu 16.04 test3
```
