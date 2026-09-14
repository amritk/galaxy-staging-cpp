# DemoApiScalarGalaxy C++ SDK Reference

## Operations

### planets.list

Get all planets

- HTTP: `GET /planets`
- Response body: `application/json`

### planets.create

Create a planet

- HTTP: `POST /planets`
- Request body: `application/json`
- Response body: `application/json`
- Errors: `400, 403`

### planets.retrieve

Get a planet

- HTTP: `GET /planets/{planetId}`
- Response body: `application/json`
- Errors: `404`

### planets.update

Update a planet

- HTTP: `PUT /planets/{planetId}`
- Request body: `application/json`
- Response body: `application/json`
- Errors: `400, 403, 404`

### planets.delete

Delete a planet

- HTTP: `DELETE /planets/{planetId}`
- Errors: `404`

### planets.uploadImage

Upload an image to a planet

- HTTP: `POST /planets/{planetId}/image`
- Request body: `multipart/form-data`
- Response body: `application/json`
- Errors: `400, 403, 404`

### celestialBodies.create

Create a celestial body

- HTTP: `POST /celestial-bodies`
- Request body: `application/json`
- Response body: `application/json`

### authentication.createUser

Create a user

- HTTP: `POST /user/signup`
- Request body: `application/json`
- Response body: `application/json`
- Errors: `400, 401, 403, 409, 422`

### authentication.createToken

Get a token

- HTTP: `POST /auth/token`
- Request body: `application/json`
- Response body: `application/json`
- Errors: `400, 401, 403`

### authentication.listMe

Get authenticated user

- HTTP: `GET /me`
- Response body: `application/json`
- Errors: `401, 403`

## Models

- `User`
- `Credentials`
- `Token`
- `CelestialBody`
- `Planet`
- `Satellite`
- `PaginatedResource`
