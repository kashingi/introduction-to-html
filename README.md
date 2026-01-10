classDiagram

class User {
  +Long id
  +String username
  +String email
  +String password
  +Boolean status
  +register()
  +login()
  +logout()
  +resetPassword()
  +searchMovies()
  +streamMovie()
  +likeMovie()
}

class Admin {
  +manageUsers()
  +activateUser()
  +disableUser()
  +manageMovies()
  +assignRole()
  +switchToUserMode()
}

class Role {
  +Long id
  +String roleName
}

class Movie {
  +Long id
  +String title
  +String description
  +String category
  +String duration
  +String videoUrl
  +uploadMovie()
  +updateMovie()
  +deleteMovie()
  +stream()
}

class Like {
  +Long id
  +Date likedAt
}

Admin --|> User
User "1" --> "1" Role : has
User "1" --> "*" Like
Movie "1" --> "*" Like
Admin "1" --> "*" Movie : manages
