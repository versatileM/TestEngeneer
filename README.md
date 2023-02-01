# TestEngeneer
import java.util.ArrayList;
import java.util.List;

public class NumberRange {
    public static String format(List<Integer> numbers) {
        StringBuilder sb = new StringBuilder();
        int start = numbers.get(0);
        int end = start;
        for (int i = 1; i < numbers.size(); i++) {
            int current = numbers.get(i);
            if (current == end + 1) {
                end = current;
            } else {
                if (start == end) {
                    sb.append(start).append(", ");
                } else {
                    sb.append(start).append("-").append(end).append(", ");
                }
                start = end = current;
            }
        }
        if (start == end) {
            sb.append(start);
        } else {
            sb.append(start).append("-").append(end);
        }
        return sb.toString();
    }

    public static void main(String[] args) {
        List<Integer> numbers = List.of(1, 2, 3, 5, 6, 7, 9, 10, 11, 12, 13);
        System.out.println(format(numbers));
    }
}

