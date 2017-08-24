
```java runnable
// { autofold
import java.io.BufferedReader;
import java.io.IOException;
import java.io.PrintWriter;
import java.nio.charset.Charset;
import java.nio.charset.StandardCharsets;
import java.nio.file.Files;
import java.nio.file.Paths;
import java.util.List;

public class Main {

public static void main(String[] args) throws Exception {

PrintWriter writer = new PrintWriter("file.txt", "UTF-8");
writer.println("Congratulations!");
writer.println("You've just read from a file \\o/");
writer.close();
// }

// Method 1: for small files (load the entire file in memory)
List<String> lines = Files.readAllLines(Paths.get("file.txt"));

// Method 2: for big files (read line by line)
try (BufferedReader reader = Files.newBufferedReader(Paths.get("file.txt"), StandardCharsets.UTF_8)) {
    reader.lines().forEach(System.out::println);
}

//{ autofold
}

}
//}

```
