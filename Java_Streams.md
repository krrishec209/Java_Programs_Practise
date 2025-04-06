Filter a list of numbers to keep only even numbers using Streams
List<Integer> list = List.of(12,4,2,23,21,35,124);
List<Integer> evenNumbers = list.stream().filter(num -> num%2 == 0).toList();
System.out.println(evenNumbers);
2. Convert a list of strings to uppercase using Streams.

List<String> strings = List.of("Java","is","a","Programming","Language");
List<String> upperCaseStrings = strings.stream().map(String::toUpperCase).toList();
System.out.println(upperCaseStrings);
3. Filter out null values from a list using Streams.

ArrayList<Integer> arrayList = new ArrayList<>();
arrayList.add(null);
arrayList.add(12);
arrayList.add(null);
arrayList.add(1234);
System.out.println(arrayList);
List<Integer> numbers = arrayList.stream().filter(Objects::nonNull).toList();
System.out.println(numbers);
4. Count the occurrences of each character in a string using Streams.

String s1 = "Hello Good Morning EveryOne";
Map<String, Long> collect = Stream.of(s1.split(""))
       .map(String::toLowerCase).collect(Collectors.groupingBy(s -> s, Collectors.counting()));
System.out.println(collect);
5. Sum all elements in a list of integers using Streams.

Integer sum = evenNumbers.stream().reduce(0, Integer::sum);
System.out.println(sum);
6. Find the maximum value in a list of numbers using Streams.

Optional<Integer> max = list.stream().max(Integer::compareTo);
System.out.println(max.get());
7. Find the minimum value in a list of numbers using Streams.

Optional<Integer> min = list.stream().min(Integer::compareTo);
System.out.println(min.get());
8. Calculate the average of a list of numbers using Streams.

Double average = list.stream().mapToInt(Integer::intValue)
          .average().orElse(0);
System.out.println(average);
9. Convert a list of integers to a comma-separated string using Streams.

String numberString= list.stream().map(String::valueOf)
        .collect(Collectors.joining(","));
System.out.println(numberString);
10. Remove duplicates from a list using Streams.

List<Integer> list = List.of(12,34,12,34,22,34,123);
List<Integer> uniqueElements = list.stream().distinct().toList();
System.out.println(uniqueElements);
11. Partition a list of integers into even and odd using Collectors.partitioningBy.

List<Integer> list1 = List.of(12,3,3,45,12,124,123,131,1901);
Map<Boolean, List<Integer>> collect = list1.stream()
          .collect(Collectors.partitioningBy(num -> num % 2 == 0));
System.out.println(collect);
12. Count elements in a list that match a certain condition.

List<Integer> list = List.of(12,34,13,34,23,33,123);
long count = list.stream().filter(num -> num % 2 == 0 && num > 10).count();
System.out.println(count);
13. Find the first element in a list that matches a condition.

List<Integer> list = List.of(12,34,13,34,23,33,123);
Integer integer = list.stream().filter(num -> num %2 ==0 && num > 10)
      .findFirst().orElse(0);
System.out.println(integer);
14. Sort a list in reverse order using Streams.

List<Integer> list = List.of(12,34,13,34,23,33,123);
List<Integer> sortedNumber = list.stream()
           .sorted(Comparator.reverseOrder()).toList();
System.out.println(sortedNumber);
15. Convert a Stream to an array of integers.

int[] arr = list.stream().mapToInt(Integer::intValue).toArray();
16. Flatten a list of lists using flatMap.

List<List<Integer>> lists = List.of(
    List.of(12,13,14,55),
    List.of(1,3,4,5),
    List.of(13,15,19,21)
);
System.out.println(lists);
List<Integer> flatList = lists.stream()
    .flatMap(List::stream).collect(Collectors.toList());
System.out.println(flatList);
17. Use Collectors.joining() to create a single string from a list of strings.

List<String> strings = List.of("Hello","Bro","Good","Morning","!");
String joinedString = strings.stream().collect(Collectors.joining(" "));
System.out.println(joinedString);
18. Merge two lists into a single list using Streams.

List<Integer> l1 = List.of(12,34,5);
List<Integer> l2 = List.of(22,21,45);
Stream<Integer> concatedStream = Stream.concat(l1.stream(),l2.stream());
concatedStream.forEach(System.out::println);


https://medium.com/@chunduriavinash16/basic-stream-operations-6c977f48d242
