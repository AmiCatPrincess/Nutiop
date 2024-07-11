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

prompt(
  'Введите числа через запятую, например "3.9, 6, 7.8, 6", без кавычек: ',
  function (input) {
    let a = input.split(',')
    console.log('Введено:', a)
    let b = 0

    a.forEach((num) => {
      b += parseFloat(num)
    })
    console.log('Среднее арифметическое данных чисел:', b / a.length)
    prompt('Нажмите Enter, чтобы выйти: ', function (input) {
      process.exit()
    })
  },
)
