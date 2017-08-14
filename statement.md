
```java runnable
// { autofold
import java.io.IOException;
import java.io.PrintWriter;
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

// Method 1: small files
List<String> lines = Files.readAllLines(Paths.get("file.txt"));

for (String line : lines) {
    System.out.println(line);
}

//{ autofold
}

}
//}
```
