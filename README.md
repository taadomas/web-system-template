# Imgur random pictures storage

## Description
    Simple web app for storing your pictures or searching for random inspirations. Everything is fully free.

## Entity definition
- [ ] Image
    - "ID": string - 16 symbols,
    - "Title": string - Max(500),
    - "Description": string - Max(500),
    - "DateCreated": ISO 8601 format date string,
    - "DateModified": ISO 8601 format date string,
    - "Content": Base64 encoded string - 4mb max.
    - "type": string - max(50)
    - "link": string - max(200)


## API definition
- [ ] Get "https://api.imgur.com/3/album/{albumID}/images""
    - Returns 200 (OK) array of Image objects
    - 401, 403

- [ ] Post "https://api.imgur.com/3/images""
    - Returns 200 (OK) uploaded new image
    - 401, 403
    
- [ ] Delete "https://api.imgur.com/3/image/{imageId}"
    - Returns 200 (OK) image deleted
    - Returns 404 (NotFound) if picture doesn't exist.
    
- [ ] Post "https://api.imgur.com/3/image/{imageId}"
    - Returns 200 (OK) image updated
    - 401, 403
    
- [ ] Post "https://api.imgur.com/oauth2/token" and pass Pin string
    - 200 authenticated and returns token
    - 403 wrong pin
    
- [ ] Redirect "https://api.imgur.com/oauth2/authorize?client_id={clientId}&response_type=token&state=APPLICATION_STATE"
    redirects to page where you can login and get Pin code


## UI definition
- [ ] https://wireframe.cc/9MHN7K
