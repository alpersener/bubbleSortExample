Bubble Sort(Sinking/Exchange Sort)
==================================

Bubble Sort,bitişik element’leri eğer yanlış sıradaysa yer değiştirerek sorted bir hale getiren bir algoritmadır.

![photo1](https://github.com/alpersener/bubbleSortExample/blob/master/photo1.png)

sort yaparken ilk pass bittiğinde en büyük eleman array’de en sonda olacaktır.

2.pass başladığında 2.en büyük sayı sondan 2.index’e geçer

3.pass başladığında 3.en büyük sayı en sondan 3.index’e geçer ve böyle böyle devam eder.

Yani her stepte en büyük eleman sona doğru geçiyor.

**İlk pass bittiğinde en sonda karşılaştırma yapmayız çünkü zaten ilk part sonunda en büyük eleman en sona geçmiş olacak yani 2.pass’ta da aynı şekilde en sonda 4 ile 5’i karşılaştırmayız bu her pass için geçerlidir.**

![photo2](https://github.com/alpersener/bubbleSortExample/blob/master/photo2.png)

![photo3](https://github.com/alpersener/bubbleSortExample/blob/master/photo3.png)

<j=length-i şeklinde değer alacaktır.

Yani i=1’de, 4 ten küçük olanları **(0,1,2,3 index’e kadar)** konrol edecektir **(1,3,4,2)**

i=2’de ,5-2=3ten küçük olanları **(yani 0,1,2 .index’e kadar)** kontrol edecektir **(1,3,2)**

i=3’de, 5-3=2den küçük olanlar **(0 ve 1.index’e kadar)** kontrol edecektir **(1,2)**

Complexity of Bubble Sort
-------------------------

`**Best case⇒O(N)’**`**dir**.Best case array sorted olursa gerçekleşir.J değeri tek tek karşılaştırılarak en sona doğru gider sonuç olarak tüm array’i gezmesi gerekir array’in n elemanı olduğu farzedilirse n adım kadar gezip compare etmesi gerekir bundan dolayı O(N)’dir.

Ek olarak array sorted olduğu için j değerleri swap’lamaz bu da onun sorted olduğunu gösterir.

`**Worst case⇒O(N^2)**`**’dir.**Worst case array opposite sorted olursa gerçekleşir örneğin array descending olarak sıralanmış(5,4,3,2,1) bunu ascending olarak istenirse eğer ya da array asceding olarak sıralanıp(1,2,3,4,5) descending olarak istenilirse worst case olmuş olacaktır.

**Örnek:Swap değerleri aşağıdaki gibi olacak**

![photo4](https://github.com/alpersener/bubbleSortExample/blob/master/photo4.png)

![photo5](https://github.com/alpersener/bubbleSortExample/blob/master/photo5.png)
    package BubbleSort;
    
    import java.util.Arrays;
    
    public class Main {
        public static void main(String[] args) {
            int[] arr={-1,7,-32,89};
            bubble(arr);
            System.out.println(Arrays.toString(arr));
    
    
        }
    
        public static void bubble(int[] arr){
            boolean swapped;
            //n-1 adımda dönecek
            for (int i = 0; i < arr.length; i++) {
                swapped=false;
                //her step'te nax item en son indexe gelecek
                for (int j = 1; j < arr.length-i; j++) {
                    //item önceki itemden küçükse swap'la
                    if(arr[j]<arr[j-1]){
                        int temp=arr[j];
                        arr[j]=arr[j-1];
                        arr[j-1]=temp;
                        swapped=true;
                    }
                }
                if(!swapped) //true
                    break;
            }
       }
    
    }

*   boolean ifadeyi vermemizin sebebi eğer array sorted ise tekrardan döngüye girip girip durmasın eğer swap yapmayacaksa ki sorted olunca swap yapamaz dursun diye
