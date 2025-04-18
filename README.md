# Projeto Sistema de Jogo de Xadrez 

## Objetivo geral: 

- Aplicar os conhecimentos aprendidos até o momento no curso para a construção de um jogo de xadrez (CLI).  

## First class: Position 

### Checklist: 

Class Position [public] 

**OOP Topics:** 

- Encapsulation
- Constructors 
- ToString (Object / overriding) 

## Starting to implement Board and Piece 

### Checklist:

Classes Piece, Board [public] 

**OOP Topics:** 

- Associations 
- Encapsulation / Access Modifiers 

**Data Structures Topics:** 

- Matrix 

## Chess layer and printing the board 

8 - - - - - - - - <br>
7 - - - - - - - - <br>
6 - - - - - - - - <br>
5 - - - - - - - - <br>
4 - - - - - - - - <br>
3 - - - - - - - - <br>
2 - - - - - - - - <br>
1 - - - - - - - - <br>
  a b c d e f g h  

### Checklist:

Methods: Board.Piece(row, column) and Board.Piece(position) 

Enum Chess.Color 

Class Chess.ChessPiece [public] 

Class Chess.ChessMatch [public]

Class ChessConsole.UI 

**OOP Topics:**  

- Enumerations 
- Encapsulation / Access Modifiers 
- Inheritance 
- Downcasting
- Static members 
- Layers pattern 

**Data Structures Topics:** 

- Matrix 

## Placing pieces on the board 

### Checklist: 

Method: Board.PlacePiece(piece, position)

Classes: Rook, King [public] 

Method: ChessMatch.InitialSetup 

**OOP Topics:** 

- Inheritance 
- Overriding 
- Polymorphism (ToString) 

## BoardException and defensive programming 

### Checklist: 
Class BoardException [public] 

Methods: Board.PositionExists, Board.ThereIsAPiece 

Implement defensive programming in Board methods 

**OOP Topics:** 

- Exceptions 
- Constructors (a string must be informed to the exception) 

## ChessException and ChessPosition 

### Checklist: 
Class ChessException [public] 

Class ChessPosition [public] 

Refactor ChessMatch.InitialSetup 

**OOP Topics:** 

- Exceptions 
- Encapsulation 
- Constructors (a string must be informed to the exception) 
- Overriding 
- Static members 
- Layers pattern 

 ## Little improvement in board printing 

### Color in terminal:

Windows: Git Bash 

Mac: Google "osx terminal color" 

### Checklist:

Place more pieces on the board 

Distinguish piece colors in UI.PrintPiece method 

## Moving pieces 

### Checklist: 

Method Board.RemovePiece 

Method UI.ReadChessPosition 

Method ChessMatch.PerformChessMove 

- Method ChessMatch.MakeMove 
- Method ChessMatch.ValidadeSourcePosition 

Write basic logic on Program.cs 

**OOP Topics:** 

- Exceptions 
- Encapsulation 

## Handling exceptions and clearing screen 

 ### Clear screen using Java: 

 https://stackoverflow.com/questions/2979383/java-clear-the-console <br>
public static void clearScreen() {   
    &emsp;System.out.print("\033[H\033[2J");   
    &emsp;System.out.flush();   
}    

### Checklist: 
ChessException

InputMismatchException 

## Possible moves of a piece 

![image](https://user-images.githubusercontent.com/81713250/136395771-52b9b2f7-cc5f-40fe-9264-630a044a55fd.png) 

 

 

 ![image](https://user-images.githubusercontent.com/81713250/136395821-95e1d893-2c29-46cb-95c8-0a9db150c21e.png)

### Checklist: 
Methods in Piece: 

- PossibleMoves [abstract] 
- PossibleMove 
- IsThereAnyPossibleMove 

Basic PossibleMove implementation for Rook and King 

Update ChessMatch.ValidadeSourcePosition 

**OOP Topics:** 

- Abstract method / class 
- Exceptions 

## Implementing possible moves of Rook 

### Checklist: 

Method ChessPiece.IsThereOpponentPiece(position) [protected] 

Implement Rook.PossibleMoves 

Method ChessMatch.ValidateTargetPosition 

**OOP Topics:** 

- Polymorphism 
- Encapsulation / access modifiers [protected] 
- Exceptions 

## Printing possible moves 

### Checklist: 

Method ChessMatch.PossibleMoves 

Method UI.PrintBoard [overload] 

Refactor main program logic 

**OOP Topics:** 

- Overloading 

## Implementing possible moves of King 

### Checklist: 

Method King.CanMove(position) [private] 

Implement King.PossibleMoves 

**OOP Topics:** 

- Encapsulation 
- Polymorphism 

 ## Switching player each turn 

### Checklist: 
Class ChessMatch: 

- Properties Turn, CurrentPlayer [private set] 
- Method NextTurn [private] 
- Update PerformChessMove 
- Update ValidadeSourcePosition 

Method UI.PrintMatch 

**OOP Topics:** 

- Encapsulation 
- Exceptions

## Handling captured pieces 

 ### Checklist: 
Method UI.PrintCapturedPieces 

Update UI.PrintMatch 

Update Program logic 

Lists in ChessMatch: _piecesOnTheBoard, _capturedPieces 

- Update constructor 
- Update PlaceNewPiece 
- Update MakeMove 

**OOP Topics:** 

- Encapsulation 
- Constructors 

**Data Structures Topics:** 

- List 

## Check logic  

### Rules: 

- Check means your king is under threat by at least one opponent piece 
- You can't put yourself in check 

 ### Checklist: 

Property ChessPiece.ChessPosition [get] 

Class ChessMatch: 

- Method UndoMove 
- Property Check [private set] 
- Method Opponent [private] 
- Method King(color) [private] 
- Method TestCheck 
- Update PerformChessMove

Update UI.PrintMatch

## Checkmate logic 

### Checklist: 
Class ChessMatch: 

- Property Checkmate [private set] 
- Method TestCheckmate [private] 
- Update PerformChessMove 

Update UI.PrintMatch 
Update Program logic

## Piece move count 

### Checklist: 

Class ChessPiece: 

- Property MoveCount [private set] 
- Method IncreaseMoveCount [internal] 
- Method DecreaseMoveCount [internal] 

Class ChessMatch: 

- Update MakeMove 
- Update UndoMove 

**OOP Topics:** 

- Encapsulation

## Pawn 

### Checklist: 
Class Pawn 

Update ChessMatch.InitialSetup 

**OOP Topics:** 

- Encapsulation 
- Inheritance 
- Polymorphism 

## Bishop 

### Checklist: 

Class Bishop 

Update ChessMatch.InitialSetup 

**OOP Topics:** 

- Encapsulation 
- Inheritance 
- Polymorphism 

## Knight 

### Checklist: 

Class Knight 
Update ChessMatch.InitialSetup 

**OOP Topics:** 

- Encapsulation 
- Inheritance 
- Polymorphism 

## Queen 

 ### Checklist: 

Class Queen 

Update ChessMatch.InitialSetup 

**OOP Topics:** 

- Encapsulation 
- Inheritance 
- Polymorphism 

## Special move - Castling 

![image](https://user-images.githubusercontent.com/81713250/136400518-9f59549a-782d-4ca8-bdf1-49c681d30580.png)

 ### Checklist: 

Update King 

Update ChessMatch.MakeMove 

Update ChessMatch.UndoMove 

## Special move - En Passant 

 ![image](https://user-images.githubusercontent.com/81713250/136400699-2168216f-86c0-4f4a-a1dc-346b98f45f74.png)

### Checklist: 

Register a pawn which can be captured by en passant on next turn 

- Property ChessMatch.EnPassantVulnerable 
- Update ChessMatch.PerformChessMove 

Update Pawn.PossibleMoves 
Update ChessMatch.MakeMove 
Update ChessMatch.UndoMove 
Update ChessMatch.InitialSetup

## Special move - Promotion 

![image](https://user-images.githubusercontent.com/81713250/136401056-9e6f969e-55c9-4667-836c-4858b8a5af72.png)

### Checklist: 
Property ChessMatch.Promoted 

Update ChessMatch.PerformChessMove 

Method ChessMatch.ReplacePromotedPiece 

Update Program logic 
