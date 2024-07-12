# Nutiop
function prompt(question, callback) {
  let stdin = process.stdin,
    stdout = process.stdout

  stdin.resume()
  stdout.write(question)

  stdin.once('data', function (data) {
    callback(data.toString().trim())
  })
}
.wrap {
  filter: drop-shadow(0 0 10px gray);
}

.element {
  display: inline-block;
  width: 111px;
  height: 111px;
  background-color: #fff;
  border-radius: 2em;
}
