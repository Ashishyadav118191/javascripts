## solution code 
## project 3

'''javasripts

const clock = document.getElementById('clock');

setInterval(function () {
  let date = new Date();
  //console.log(date.toLocaleString());
  clock.innerHTML = date.toLocaleTimeString();
}, 1000);

'''