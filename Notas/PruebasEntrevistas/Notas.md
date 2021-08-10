
![image](https://user-images.githubusercontent.com/31891276/128776933-a345c22f-7753-4b4a-852b-e81f6d52e968.png)


myArray.sort();
    max = myArray[myArray.length - 1];

    for(var i = 1; i <= max; i++){

        process.stdout.write(i + ": ");
        for (var x = 0; x < myArray.length; x++){
            if (i == myArray[x]){
                process.stdout.write("*");
            }
        }
       console.log("");
    }
