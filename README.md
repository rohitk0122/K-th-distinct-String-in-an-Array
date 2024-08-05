# K-th-distinct-String-in-an-Array
class Solution {
    public String kthDistinct(String[] arr, int k) {
       Map<String, Integer> frequencyMap = new LinkedHashMap<>();

        // Count the frequency of each string
        for (String s : arr){
            frequencyMap.put(s, frequencyMap.getOrDefault(s, 0) + 1);
        }
        int count = 0;
        for (String s : arr){
            if (frequencyMap.get(s) == 1){
                count++;
                if (count == k){
                    return s;
                }
            }
        }

        return "";  
    }
}
