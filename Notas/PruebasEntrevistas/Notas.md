
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

![image](https://user-images.githubusercontent.com/31891276/150459402-e193d45f-680a-4c4d-a060-b2c7ac5a559c.png)

![image](https://user-images.githubusercontent.com/31891276/150459447-d988ad0b-51bf-4e1a-b95c-4bedd82f7013.png)



    static int[] myArray = {13,2,4,35,1};
    public static void main (String args[]) {
        int max =  Arrays.stream(myArray).max().getAsInt();
        System.out.println(max);
    }
    
![image](https://user-images.githubusercontent.com/31891276/150455936-d0507890-b985-4bf7-b7bf-c907039600f3.png)

![image](https://user-images.githubusercontent.com/31891276/150455970-fd4de402-7591-4210-a4f4-c46eaf3d23ab.png)

![image](https://user-images.githubusercontent.com/31891276/150456131-ec93e495-830c-4063-bb68-5b0591087b0a.png)

![image](https://user-images.githubusercontent.com/31891276/150456236-8a455f2a-f14d-4be8-8b2e-174e80bf07ba.png)

![image](https://user-images.githubusercontent.com/31891276/150456825-ab725ffc-34fe-4969-b4b8-309a455a0728.png)

NO estoy seguro

![image](https://user-images.githubusercontent.com/31891276/150456932-da386c46-139d-4745-ab95-e43d125a0ab0.png)

![image](https://user-images.githubusercontent.com/31891276/150457894-28407785-e41f-43df-9395-b676bb1bfc4f.png)

![image](https://user-images.githubusercontent.com/31891276/150459698-361d3e1d-e0f6-4f1b-85fa-1888efc2d4ce.png)

![image](https://user-images.githubusercontent.com/31891276/150459880-c3334792-6b0c-4b7e-ae0d-98d9c889fdee.png)



static int[] myArray = {1,3,4,2,7,0};

public static void main (String args[]) {
   for(int i=0; i<myArray.length-1; i++){
            for(int j=1;j<myArray.length;j++){
                if(myArray[i]+myArray[j]==10){
                    System.out.println(myArray[i]+" "+myArray[j]);
                    j=myArray.length+1;
                    i=myArray.length+1;
                }
            }
        }
}


![image](https://user-images.githubusercontent.com/31891276/150459947-485a264f-50dd-427d-bfe3-fe16a4460299.png)



![image](https://user-images.githubusercontent.com/31891276/150460031-5ea73ce0-e34b-4c77-a9a9-d45f8412f3b3.png)

