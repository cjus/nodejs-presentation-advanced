## Login Request

### In routes/login.js we have:

```
/**
 * @name loginUser
 * @description Login helper function. Makes API call to api/v1/login
 * @param email {string}
 * @param password {string} << should be hashed in actual use!
 */
function loginUser(email, password) {
  var request = $.post('api/v1/login', {
    email: email,
    password: password
  });
  request.done(function(data) {
    $('.status').text('Login successful');
  });
  request.fail(function(err) {
    $('.status').text('Login unsuccessful');
  });
}
```