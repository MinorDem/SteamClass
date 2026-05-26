# index.html Maintenance Guide

This document describes the purpose of each maintained `index.html` entry page in this project.

Scope:
- Included: files named exactly `index.html`.
- Excluded: `0index.html`, `1index.html`, and any other HTML file whose filename starts with a number.
- This is for maintenance only; it does not describe every alternate prototype or backup HTML file.

## File Guide

| File | Purpose |
| --- | --- |
| `1NumGuess/index.html` | Number Guessing Game. Main ranked page where players guess a hidden number across difficulty levels and submit completion scores to the leaderboard. |
| `2SlidingPuzzle/index.html` | Main sliding number puzzle page for board sizes from 3x3 to 10x10, with ranked leaderboards by size and auto-solve protection. |
| `2SlidingPuzzle/submit/index.html` | Alternate/submission version of the sliding puzzle page. Uses the same sliding puzzle leaderboard key pattern and is kept as a separate playable entry. |
| `3HitTarget/index.html` | Hit the Target game. Players click targets under difficulty settings and submit ranked time/score results. |
| `4WordGuess/index.html` | Five-letter Word Guess game. Main ranked word puzzle page with leaderboard preview and win submission. |
| `5SnakeRun/index.html` | Snake game with easy, medium, and hard modes. Tracks wins and best time through the shared leaderboard API. |
| `6IntlChess/index.html` | Main offline Chess vs Computer page, including bundled chess logic and difficulty-based leaderboards. |
| `6IntlChess/chess_deploy_bundle/index.html` | Deployable bundled copy of Chess vs Computer. Keep in sync with the main chess page when deployment bundle behavior changes. |
| `7FishCatching/index.html` | Fishing game. Main ranked page where players catch targets/fish and submit results to difficulty leaderboards. |
| `8FlappyBird/index.html` | Flipping Bird game. Survival-time arcade page with leaderboard submission after each run. |
| `9Cooking/index.html` | Dish Maker cooking game. Players assemble dishes by dragging/selecting ingredients, with ranked boards per difficulty. |
| `10CountSeconds/index.html` | Seconds Challenge hub for 10, 20, and 30 second timing challenges, with separate leaderboards for each target duration. |
| `11MemoryMatch/index.html` | Emoji Memory Match game. Players match hidden cards and submit ranked completion times. |
| `12Checker/index.html` | Checkers vs Computer page. Ranked board game against a computer opponent with leaderboard submission on wins. |
| `13WordGuess6/index.html` | Six-letter Word Guess game. Ranked word puzzle page with leaderboard preview and win submission. |
| `14MathSpeed/index.html` | Math Speed Quiz. Timed arithmetic quiz with difficulty levels and leaderboard submission. |
| `15FindDifference/index.html` | Find the Different Character game. Players locate the odd character; leaderboard records time and wrong-click performance. |
| `16WordGuess7/index.html` | Seven-letter Word Guess game. Ranked word puzzle page with leaderboard preview and win submission. |
| `17Pipes/index.html` | Pipes / FreeNet puzzle. Players connect pipe networks on size-based boards and submit completion times. |
| `18Uno/index.html` | UNO Rush ranked card game. Players race to empty their hand, then submit win time to the shared UNO leaderboard. |
| `19FlowFree/index.html` | Flow Links ranked puzzle. Players connect matching colored dots and fill the board, with leaderboards by grid size. |
| `20FightTheLandlord/index.html` | Fight the Landlord card game. Single player versus two computer players with leaderboard submission on wins. |
| `21GuessTheAnimal/index.html` | Mystery Picture animal guessing game. Players identify animals from partial reveals; leaderboard records successful completions. |
| `22Trivia/index.html` | Science Speed Quiz. Timed science trivia page with difficulty-aware scoring and leaderboard integration. |
| `23SideFinishRun/index.html` | Side Finish Run platform game. Players climb alternating platforms, collect coins, reach finish, and submit ranked times. |
| `24Puzzle/index.html` | Pieces Puzzle ranked image puzzle. Players choose an image and difficulty, assemble pieces, and submit completion times. |
| `25BrickBreaker/index.html` | Brick Breaker ranked arcade game. Players clear brick walls, with difficulty-based leaderboard boards. |
| `26ColorLink/index.html` | Color Link game. Players match color names to tiles through rounds; one mistake ends the game. |
| `28ArtQuizzes/index.html` | Roma Aeterna trivia/art quiz page. Quiz-style ranked page with leaderboard calls through the shared API. |
| `29CrossWord/index.html` | Science Crossword ranked puzzle. Main crossword entry with difficulty settings and leaderboard submission. |
| `29LadderClimb/index.html` | Ladder Climb ranked path game. Players climb from bottom to top through safe steps; wrong choices trigger fail animation. |
| `87MineSweeper/index.html` | Mines ranked puzzle. Players reveal safe tiles and avoid hidden mines on difficulty-based boards. |
| `90MemoryPath/index.html` | Memory Path ranked sequence game. Players watch and repeat longer/faster patterns, then submit completion times. |
| `feedback/index.html` | Feedback Board page. Non-game page for collecting and showing feedback. Maintain separately from ranked game logic. |
| `rank/index.html` | All Puzzle Rank page. Aggregates leaderboard data from `/api/leaderboard` across game keys for a project-wide ranking view. |

## Maintenance Notes

- Most ranked games use the shared `/api/score` POST endpoint and `/api/leaderboard` GET endpoint.
- Game-specific leaderboard keys are usually stored in `BASE_GAME_ID`, `GAME_ID`, or a helper such as `gameId()`.
- When changing scoring or difficulty names, update both score submission and leaderboard loading code.
- If a deployment copy exists, such as the chess deploy bundle, update both the source page and deploy copy when behavior should remain identical.
