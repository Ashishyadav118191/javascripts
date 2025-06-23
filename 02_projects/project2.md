# solution code 

## project 2

''' javascripts

const form = document.querySelector('form');

form.addEventListener('submit', function (e) {
  e.preventDefault();

  const height = parseInt(document.querySelector('#height').value);
  const weight = parseInt(document.querySelector('#weight').value);
  const results = document.querySelector('#results');

  if (height == '' || height < 0 || isNaN(height)) {
    results.innerHTML = `${height}`;
  } 
  else if (weight == '' || weight < 0 || isNaN(weight)) {
    results.innerHTML = `${weight}`;
  } 
  else {
    const bmi = (weight / ((height * height) / 10000)).toFixed(2);
    
    if (bmi < 18.6) {
      results.innerHTML = `<span>${bmi},Under weight</span>`;
    }
    if (bmi>=24.90&&bmi <= 18.6  ) {
      results.innerHTML = `<span>${bmi},Normal</span>`;
    }
    if(bmi > 24.90){
      results.innerHTML = `<span>${bmi},Over weight</span>`;
    }
  }
});
'''
