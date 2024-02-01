---
toc: true
comments: true
layout: post
title: Login
type: hacks
courses: { compsci: {week: 9} }
---

<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Login Page</title>
    <link rel="stylesheet" href="styles.css">
</head>

<body>
    <div id="errorMessage"></div>
    <form onsubmit="login_user(event)">
        <p>
            <label for="uid">User ID:</label>
            <input type="text" name="uid" id="uid" required>
        </p>
        <p>
            <label for="password">Password:</label>
            <input type="password" name="password" id="password" required>
        </p>
        <p>
            <button class="button-spacing" type="submit">Log In</button>
            <button onclick="window.location.href='https://tanav-kambhampati.github.io/student2/'" class="button-spacing">Sign Up</button>
        </p>
    </form>

    <script>
        function login_user(event) {
            event.preventDefault();

            const enteredUid = document.getElementById("uid").value;
            const enteredPassword = document.getElementById("password").value;

            const myHeaders = new Headers();
            myHeaders.append("Accept", "*/*");
            myHeaders.append("Accept-Language", "en-US,en;q=0.9");
            myHeaders.append("Content-Type", "application/json");

            const raw = JSON.stringify({
                "uid": enteredUid,
                "password": enteredPassword
            });

            const requestOptions = {
                method: 'POST',
                headers: myHeaders,
                body: raw,
                redirect: 'follow'
            };

            fetch("http://127.0.0.1:8086/api/users/authenticate", requestOptions)
                .then(response => {
                    if (response.ok) {
                        console.log("User logged in successfully");
                        window.location.href = "https://tanav-kambhampati.github.io/student2/";
                    } else {
                        console.error("User login failed");
                        const errorMessageDiv = document.getElementById('errorMessage');
                        errorMessageDiv.innerHTML = '<label style="color: red;">User Login Failed</label>';
                    }
                })
                .catch(error => console.log('error', error));
        }
    </script>
</body>

</html>