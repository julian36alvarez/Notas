
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



![image](https://user-images.githubusercontent.com/31891276/150453070-4fe0ba77-9d27-4d5a-95af-202e042b2ac0.png)



![image](https://user-images.githubusercontent.com/31891276/150453804-2b4447db-54c3-47d0-8d49-373a25259c08.png)

![image](https://user-images.githubusercontent.com/31891276/150453794-93393e71-1cca-42be-957a-691699b582eb.png)

![image](https://user-images.githubusercontent.com/31891276/150453878-c9c00bdf-972d-455e-9541-96b7f3814aa2.png)

![image](https://user-images.githubusercontent.com/31891276/150454137-652478f3-9631-4d9d-865b-b93799dd494d.png)

![image](https://user-images.githubusercontent.com/31891276/150454156-3656f70a-87ab-4bf2-8a89-b4022b8791dd.png)

![image](https://user-images.githubusercontent.com/31891276/150455561-258d38e9-caf3-4b5b-b1d4-b6592cac5523.png)

    static int[] myArray = {13,2,4,35,1};
    public static void main (String args[]) {
        int max =  Arrays.stream(myArray).max().getAsInt();
        System.out.println(max);
    }
    
![image](https://user-images.githubusercontent.com/31891276/150455936-d0507890-b985-4bf7-b7bf-c907039600f3.png)

![image](https://user-images.githubusercontent.com/31891276/150455970-fd4de402-7591-4210-a4f4-c46eaf3d23ab.png)



