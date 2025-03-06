GET request puts user parameters such as file uploads and user credentials in the URL. POST puts the same parameters in request body. Benefits of putting parameters in request body:
- More data can be sent per request. Good for sending large files.
- Lack of logging of large file uploads reduces workload for the server. Also, sensitive information such as passwords are not exposed in the log.
- Less encoding of characters is required. It is less of a hassle for manual input.
- 