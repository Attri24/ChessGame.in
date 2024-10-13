![Chess](https://github.com/user-attachments/assets/69b660d8-ba29-4611-94ff-539baa685638)


# Multiplayer Chess Game with Express, Socket.io, and Chess.js

This is a simple real-time multiplayer chess game built with **Node.js**, **Express**, **Socket.io**, and **Chess.js**. It allows two players (White and Black) to play chess online, while additional users can connect as spectators and observe the game in real time.

## Features
- **Multiplayer Support**: Allows two players to play chess, one as white and one as black.
- **Real-Time Updates**: Moves are broadcast to all connected clients (both players and spectators) in real-time using WebSockets.
- **Spectator Mode**: Additional users who connect after two players are assigned will be spectators and can watch the game in real time.
- **Move Validation**: Uses `Chess.js` to validate moves and ensures only the current player (white or black) can make a move.
- **Board State Broadcasting**: The board state is continuously sent to all clients, ensuring everyone is always in sync.
- **Player Roles**: Assigns the first player as white, the second as black. New players that join when both slots are filled become spectators.

## Prerequisites

To run this project, you will need to have the following installed:
- **Node.js** (version 12 or higher)
- **npm** (Node package manager)

## Getting Started

### 1. Clone the repository




### 2. Install Dependencies

bash
npm install


This will install all the required dependencies, such as:
- express
- socket.io
- chess.js
- ejs

### 3. Run the Server

bash
npm start

This will start the server on `http://localhost:3000`.

### 4. Access the Game

Open your browser and go to `http://localhost:3000`. You can open multiple tabs to simulate multiple users (e.g., one for the white player, one for the black player, and any additional ones for spectators).

## File Structure


chess-multiplayer/
├── public/
│   └── [static assets like CSS, JS, etc.]
├── views/
│   └── index.ejs          # Main HTML page with the chessboard
├── app.js                  # Main backend logic (Express + Socket.io)
├── package.json            # Project details and dependencies
├── README.md               # This file


## Functionality Explanation

### 1. **Player Assignment**
- The first connected client is assigned the **white** player role.
- The second connected client is assigned the **black** player role.
- All other clients are designated as **spectators**, and they can watch the game unfold in real time.

### 2. **Real-Time Game**
- Each player can make moves on their turn. Only the player whose turn it is can make a move (white goes first).
- Moves are broadcast to all connected clients (including spectators) using WebSockets.
- The current board state is maintained and shared with all clients to ensure synchronization.

### 3. **Move Validation**
- The server uses the `Chess.js` library to validate the moves:
  - If the move is valid, it will update the game state and broadcast the move to all clients.
  - If the move is invalid, it sends an error back to the player who made the invalid move.

### 4. **Spectator Mode**
- Spectators are automatically assigned if the white and black player slots are already filled.
- Spectators receive real-time updates of the game (including moves and board state) but cannot make moves.

### 5. **Player Disconnection**
- If a player (white or black) disconnects, their spot is freed up, allowing a new player to join and take that role.
- The game can continue as long as two players (white and black) are connected.

## Technologies Used

- **Node.js**: Backend runtime environment
- **Express**: Web framework for Node.js
- **Socket.io**: Real-time communication between the server and clients
- **Chess.js**: JavaScript library for chess move validation and game logic
- **EJS**: Template engine for rendering the front-end (chessboard)

## Future Improvements

- **Save/Resume Games**: Add functionality to save the current game state and allow players to resume the game if the server restarts.
- **Spectator Chat**: Add a chat feature for spectators to discuss the game while watching.
- **AI Opponent**: Implement an AI player using a chess engine for solo play.
- **Multiple Game Rooms**: Extend the functionality to allow multiple chess games to be played simultaneously in different rooms.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

Feel free to contribute to this project by opening issues or submitting pull requests. Enjoy playing chess!
 
