import java.util.Arrays;

public class NextPermutation {

    public static void nextPermutation(int[] arr) {
        int n = arr.length;
        int i;

        for (i = n - 2; i >= 0; i--) {
            if (arr[i] < arr[i + 1]) {
                break;
            }
        }

        if (i >= 0) {
            for (int j = n - 1; j > i; j--) {
                if (arr[j] > arr[i]) {
                    int temp = arr[i];
                    arr[i] = arr[j];
                    arr[j] = temp;
                    break;
                }
            }
        }

        int start = i + 1;
        int end = n - 1;
        while (start < end) {
            int temp = arr[start];
            arr[start] = arr[end];
            arr[end] = temp;
            start++;
            end--;
        }
    }

    public static void main(String[] args) {
        int[] arr = {1, 3, 5, 4, 2};
        nextPermutation(arr);
        System.out.println(Arrays.toString(arr));
    }
}
