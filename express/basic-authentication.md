###Basic Authentication  
  
**Client side**: set header's `Authorization` as `"Basic <a base 64 encrypt user:password string>"` along with a request  
**Server side**: to decode the `req.headers.authorization` to see:  
  1. whether authorization is set  
  2. whether user / password are all correct  

Otherwise, return `401 error` and finish the response with `res.end(err.message);`  

**Sample Code**:  
  
```
function auth (req, res, next) {
    console.log(req.headers);
    var authHeader = req.headers.authorization;
    if (!authHeader) {
        var err = new Error('You are not authenticated!');
        err.status = 401;
        next(err);
        return;
    }
    var auth = new Buffer(authHeader.split(' ')[1], 'base64').toString().split(':');
    var user = auth[0];
    var pass = auth[1];
    if (user == 'admin' && pass == 'password') {
        next(); // authorized
    } else {
        var err = new Error('You are not authenticated!');
        err.status = 401;
        next(err);
    }
}
app.use(auth);
app.use(function(err,req,res,next) {
            res.writeHead(err.status || 500, {
            'WWW-Authenticate': 'Basic',
            'Content-Type': 'text/plain'
        });
        res.end(err.message);
});
```
