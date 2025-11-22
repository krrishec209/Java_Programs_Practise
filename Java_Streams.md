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

***************************************


“𝐈 𝐚𝐬𝐤𝐞𝐝 𝐦𝐲 𝐦𝐞𝐧𝐭𝐨𝐫 𝐰𝐡𝐲 𝐉𝐚𝐯𝐚 𝐒𝐭𝐫𝐞𝐚𝐦𝐬 𝐚𝐫𝐞 𝐜𝐨𝐧𝐬𝐢𝐝𝐞𝐫𝐞𝐝 𝐟𝐚𝐬𝐭𝐞𝐫 𝐭𝐡𝐚𝐧 𝐧𝐨𝐫𝐦𝐚𝐥 𝐥𝐨𝐨𝐩𝐬… 𝐚𝐧𝐝 𝐡𝐢𝐬 𝐚𝐧𝐬𝐰𝐞𝐫 𝐛𝐥𝐞𝐰 𝐦𝐲 𝐦𝐢𝐧𝐝! ⚡🔥”

Me (curious):
 “People keep saying Streams are faster than loops in Java…
 but how? Isn’t a for loop the most basic, efficient thing?”

Mentor (smiling):
 “Ah, that’s what everyone thinks at first. But Streams don’t just loop…
 they bring parallelism, batching, and low-level optimizations to the table.”

Me: “Parallelism? Like multithreading?”

Mentor: “Exactly. Let me show you.”

🏭 𝐇𝐢𝐬 𝐫𝐞𝐚𝐥-𝐰𝐨𝐫𝐥𝐝 𝐞𝐱𝐚𝐦𝐩𝐥𝐞 (that changed everything)
“Imagine you run a warehouse with 10,000 packages.

Using a normal loop is like:
🧍 One person opening packages
 One at a time
 Start → end → done

But Streams — especially parallel streams — work like this:
🧑‍🤝‍🧑 8 workers
 Each taking a portion of the boxes
 All working at the same time
 Finish much faster
Same task.
 Different strategy.
 Massive performance jump.”

Me: “Ohhh… so Streams split the work behind the scenes?”

Mentor:
 “Correct. They take advantage of all your CPU cores.
 Your loop usually uses only one.”

⚙️ 𝐁𝐮𝐭 𝐭𝐡𝐞𝐧 𝐡𝐞 𝐝𝐫𝐨𝐩𝐩𝐞𝐝 𝐭𝐡𝐞 𝐫𝐞𝐚𝐥 𝐛𝐨𝐦𝐛… 💣
Mentor: “Parallelism is just the start.
 
Streams also give you optimizations that loops don’t…”
✔ Lazy evaluation
 ✔ Fewer branch predictions
 ✔ Optimized internal iteration
 ✔ CPU-level vectorization in some cases
 ✔ Native-like processing pipelines

Me (shocked): “So… Streams are basically a high-performance engine hidden in simple syntax?”

Mentor (laughs): “Exactly! You write simple code.
 Java does heavy optimization under the hood.”

🧠 𝐓𝐡𝐞 𝐩𝐚𝐫𝐭 𝐭𝐡𝐚𝐭 𝐬𝐭𝐮𝐧𝐠 𝐦𝐞 𝐚 𝐛𝐢𝐭…
Mentor:
 “But remember — Streams are not always faster.”

Me: “What? Why?”

Mentor:
 “For small collections, the overhead of creating the Stream pipeline can make it slower.

 But for large datasets and CPU-heavy tasks…
Streams stop being syntax…
 and become infrastructure.”

Me (mind blown 🤯):
 “So when I use Streams, I’m not just writing prettier code…
 I’m unlocking performance features I never manually code in loops!”

Mentor:
 “That’s the spirit.
 Use loops for simplicity.
 Use Streams for power.”

Follow Arun Kumar for more



<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/8fcf6e28-3eb8-42f4-bfc5-78a7b9b14f99" />


<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/78b032e8-02cd-4c5e-9d12-1b2d2693303b" />


<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/649870ed-1fcf-4945-8d28-3efe8985ea79" />



<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/96278776-f7f3-49c8-89e9-fb84a6b17c67" />


<img width="1024" height="1536" alt="image" src="https://github.com/user-attachments/assets/3dabde79-a6c2-49ef-baf1-6253de1e6620" />

https://www.linkedin.com/posts/arunsks98_java-javadeveloper-javastreams-ugcPost-7397584564401127424-DmiI?utm_source=share&utm_medium=member_desktop&rcm=ACoAAARSzbgBGEbWHnTkxyPnkFaeZcnK-pW0lqg

