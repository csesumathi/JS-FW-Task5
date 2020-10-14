# JS-FW-Task5

var request=new XMLHttpRequest();
request.open('GET','https://restcountries.eu/rest/v2/all','true')

request.send()
request.onload=function(){
    var data=JSON.parse(this.response)
    console.log(data)
    var arr=[]
    var country=data.filter(ele=>ele.region=='Asia')
        arr.push(country)
        //console.log(country,country.length)
        console.log(arr,arr.length)
    //print all the countries,where population is less than 2lacs
    var population=data.filter(ele=>ele.population<200000)
    console.log(population)

    //print name,flag,capital using forEach function
    data.forEach(element => {
        //console.log("Name:     Flag:          Capital")
        console.log(element.name,element.flag,element.capital)
    });
  
    var totalpopulation=data.reduce((result,ele,i)=>{return result+ele.population},0)
    console.log("total population:"+totalpopulation)

   var asia=data.filter(ele=>ele.region==='Asia').reduce((result,ele,i)=>{return result+ele.population},0)
   console.log("AsiaPopulation:"+asia)
    


var usdcountry=function(){
    for(var i=0;i<data.length;i++)
    {
        var currency=data[i].currencies
        //console.log(currency)
        for(var j=0;j<currency.length;j++)
        {
            if(currency[j].code==="USD")
            {
                console.log(data[i])
            }
        }
    }
}
 usdcountry(data)
   
// var us=data.filter((ele)=>ele.currencies[0].code==="USD")
// console.log(us)
// var us=data.map((ele,i)=>ele.currencies)
//  var f=us.filter(e=>e[0].code==="USD")
// console.log(f)


}

var xhr = new XMLHttpRequest();

    xhr.onreadystatechange=function() {
    
        if (xhr.readyState === 4){   //if complete
            if(xhr.status === 200){  //check if "OK" (200)
                //success
            }
        }

    else{
  
    try {
        xhr.open('GET','https://restcountries.eu/rest/v2/all ', false);
    }
    catch(err){
        alert(err.message);
    }
    
        
    }
    }

xhr.send();
