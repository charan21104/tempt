
//. Using Lambda & Stream API: Create a List of 15 integers.
//Print even numbers.
//Find sum of numbers using reduce().
//Sort in descending order.




package program2;

import java.util.*;

public class NumberPlay {
    static void main() {
        List<Integer> numList= Arrays.asList(1,2,3,4,5,6,7,8,8,9,6,4,5,2,3);

        numList.stream().filter(n->n%2==0).forEach(System.out::println);
        System.out.println();

        int sum=numList.stream().reduce((x,y)->x+y).get();

        System.out.println(sum);

        System.out.println();
        Collections.sort(numList,new NumCompare());

        numList.stream().forEach(System.out::println);
    }
}

class NumCompare implements Comparator<Integer>{

    @Override
    public int compare(Integer o1, Integer o2) {
        return o2.compareTo(o1);
    }
}
