# formulario-js
//Matheus Henrique e mykaellen 

!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <form>
    <h3>Dados Pessoais :</h3>
    <p>nome : <input id="n1" required></p>
    <p>nascimento :  <input type="date"  min="1920-01-01" max="2005-03-24" id="date1" required>
    <p>nome da mãe : <input  id="n2" required></p>
    <p>nome do pai : <input id="n3" required></p>
    <p>telefone : DDD <input  id="numb1" required> tel: <input required> ramal <input></p>
    <p>email : <input type="email" id="email" onblur="checarEmail()" required></p>
    <h3>informações de Matricula :</h3> <p id="t1">turno:</p>  </p>
    <p>serie: <select name="seriee" id="s1">
        <option value="fundamental">fundamental</option>
        <option value="medio">medio</option>
        <option value="superior">superior</option>
    </select></p>
    <p>atividades extracurriculares:</p>   <p id="l1">manhã <input type="radio"></p>
    <p>informatica <input name="check" type="checkbox" onclick="d2()"></p> <p id="l2">tarde<input type="radio"></p>
    <p>musica <input name="check" type="checkbox" onclick="d2()" ></p>
    <p>balet <input name="check" type="checkbox" onclick="d2()" ></p>
    <p>pintura <input name="check"  type="checkbox" onclick="d2()" ></p>
    <p>judô <input name="check"  type="checkbox" onclick="d2()" ></p>
    <p>futebol <input name="check"  type="checkbox" onclick="d2()" ></p>
    <p id="test"></p>
    <button type="button" onclick="checarEmail(); checarddd();">Enviar Formulario</button>   <button type="reset">Limpar Campos</button>
<p id="test"></p>
     </form>
    <style>
        p#t1{
            position: absolute;
            left: 18%;
            
        }
        p#l1{
            position: absolute;
            left: 18%;
            
        }
        p#l2{
            position: absolute;
            left: 18%;
            
        }
    </style>
<script>
function checarddd() {
   
    let ddd = document.getElementById("numb1").value;
    let dd2 = ["11", "12","13","14","15","16", "17","18", "19", "21","22","24","27","28","31","32","33","34","35","37","38","41","42","43","44","45","46","47","48","49","51","53","54","55","61","62","63","64","65","66","67","68","69","71","73","74","75","77","79","81","82","83","84","85","86", "87", "88", "89", "91","92","93","94", "95", "96","97","98","99"]
    if(dd2.includes(ddd)){ // se dd2 estiver incluso em ddd
        document.getElementById("numb1").innerHTML = ddd //subistituir posição 'numb1' por ddd
        alert("parabéns você concluio seu cadastro!!")
    }
   else{
    alert("você esta cometendo um erro em DDD")
   }
   document.getElementById("test").innerHTML = emaill

  
  
  
}

    

function d2(){
 let boxes = document.getElementsByName("check"); // ler todos os nomes que pussir check
 let limit = 3;
 let contador = 0;
 for (let i = 0; i < boxes.length;i++){ // se variavel [i] -= posição 0; variavel i < que boxes; adicione mais um
    if(boxes[i].checked){ //se boxes variavel [i] checado
        contador++; // adicionar mais um
    if(contador > limit){ //se contador for maior que limite
        alert("você esta excedendo o limite, aceitamos apenas 3 opções");
        boxes[i].checked = false; //se boxes for igual a falso
        contador--; // diminuir um
    }
    }
 }



}
  
function checarEmail(){
if( document.forms[0].email.value=="" 
   || document.forms[0].email.value.indexOf('@')==-1  //checar se pelomenos em um local de email vai possuir um arroba
     || document.forms[0].email.value.indexOf('.')==-1 ) //checar se pelomenos em um local de email vai possuir um .
    {
      alert( "por favor, informe um E-MAIL válido!" );
      return false;
    }
  return true
}
      



  

</script>
