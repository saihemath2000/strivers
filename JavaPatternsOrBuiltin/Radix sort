class Solution {
    public static void countSort(int[] arr, int exp) {
        int n = arr.length;
        int[] output = new int[n];
        int[] count = new int[10];

        Arrays.fill(count,0);

        for(int i=0; i<n; i++) {
            count[(arr[i]/exp) % 10]++ ;
        }

        for(int i=1; i<10; i++) {
            count[i] += count[i-1];
        }

        for (int i = n - 1; i >= 0; i--) {
            output[count[(arr[i] / exp) % 10] - 1] = arr[i];
            count[(arr[i] / exp) % 10]--;
        }

        for (int i = 0; i < n; i++) {
            arr[i] = output[i];
        }
    }
    public int maximumGap(int[] arr) {
        if (arr.length < 2) return 0;
        int max = Arrays.stream(arr).max().getAsInt();
        for(int exp = 1; max/exp > 0; exp *= 10) {
            countSort(arr,exp);
        }
        int diff  = 0; 
        for (int i=1; i<arr.length; i++) {
            diff = Math.max(diff, arr[i] - arr[i-1]);
        }
        return diff;
    }
}
