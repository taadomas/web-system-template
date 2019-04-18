# Imgur random pictures storage

## Description
    Simple web app for storing your pictures or searching for random inspirations. You can upload pictures as public ones (that everyone can see) or store them in your personal cloud based storage. Everything is fully free.

## Entity definition
- [ ] Picture
    - "ID": string (GUID),
    - "Title": string,
    - "Description": string,
    - "DateCreated": ISO 8601 format date string,
    - "DateModified": ISO 8601 format date string,
    - "Author": string (author id)
    - "PublicPhoto": boolean
    - "Content": string (base64 encoded content)


## API definition
- [ ] Get "Hostname/picture/{ID}"
    - Returns 200 (OK) specific picture object by ID
    - Returns 404 (NotFound) if picture doesn't exist.
    - Returns 401 (NotAuthorized) if you are not logged in.

- [ ] Get "Hostname/pictures?filter=filter&itemsinpage=5%page=2"
    - Returns 200 (OK) and {itemsinpage or default 10} pictures while skipping {page x itemsinpage or default 0} pictures of your pictures (taking your id from token) that matches not mandatory filter {filter}
    - Returns 200 with empty list if no pictures matches request.
    - Returns 401 (NotAuthorized) if you are not logged in.
    
- [ ] Get "Hostname/public/picture/{ID}"
    - Returns 200 (OK) specific picture object by ID
    - Returns 404 (NotFound) if picture doesn't exist.
    
- [ ] Get "Hostname/public/pictures?filter=filter&itemsinpage=5%page=2"
    - Returns 200 (OK) and {itemsinpage or default 10} pictures while skipping {page x itemsinpage or default 0} pictures of public pictures that matches not mandatory filter {filter}
    - Returns 200 with empty list if no pictures matches request.
    
- [ ] Post "Hostname/picture/uploadPicture" and pass Picture object
    - 202 if picture uploaded
    - 401 if not logged in
    - 500 if some internal errors occured
    
- [ ] Delete "Hostname/picture/{id}"
    - 200 deleted
    - 404 not found
    - 401 not logged in
    - 403 not your picture
    
- [ ] Delete "Hostname/public/picture/{id}"
    - 200 deleted
    - 404 not found
    - 401 not logged in
    - 403 not your picture
    
- [ ] Update "Hostname/picture/{id}" with picture object
    - 200 updated
    - 404 not found
    - 401 not logged in
    - 403 not your picture
    
- [ ] Update "Hostname/public/picture/{id}" with picture object
    - 200 updated
    - 404 not found
    - 401 not logged in
    - 403 not your picture

## UI definition
- [ ] https://wireframe.cc/9MHN7K
