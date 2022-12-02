### Task 7 kyu

[Task link](https://www.codewars.com/kata/554b4ac871d6813a03000035/)

In this little assignment you are given a string of space separated numbers, and have to return the highest and lowest number.
Examples

highAndLow("1 2 3 4 5")  // return "5 1"
highAndLow("1 2 -3 4 5") // return "5 -3"
highAndLow("1 9 3 4 -5") // return "9 -5"

Notes

    All numbers are valid Int32, no need to validate them.
    There will always be at least one number in the input string.
    Output string must be two numbers separated by a single space, and highest number is first.



### My solution

```Java
public class Kata {
    public static String highAndLow(String numbers) {

        String[] splitStr = numbers.split(" ");
        int lNum = Integer.parseInt(splitStr[0]);
        int hNum = Integer.parseInt(splitStr[0]);
        for(int i=1; i<splitStr.length; i++){
            if(lNum>Integer.parseInt(splitStr[i]))
                lNum = Integer.parseInt(splitStr[i]);
            if(hNum<Integer.parseInt(splitStr[i]))
                hNum = Integer.parseInt(splitStr[i]);
        }


        return  String.valueOf(hNum)+" "+ String.valueOf(lNum);
    }
}
```

### Favourite solution from code-wars

```Java

public class Kata {
    public static String highAndLow(String numbers) {
        int x;
        int h = 0;
        int l = 0;
        boolean startSet = false;
        String p = "";

        for(int i = 0; i < numbers.length(); i++){
            if(numbers.charAt(i) != 32){
                p += numbers.charAt(i);
            }
            if(numbers.charAt(i) == 32 || i + 1 == numbers.length()){
                x = Integer.parseInt(p);
                p = "";
                if(!startSet){
                    h = x;
                    l = x;
                    startSet = true;
                }
                if(x > h) h = x;
                if(x < l) l = x;
            }
        }
        return h + " " + l;
    }
}

```

Strange solution!

# Have a nice day!