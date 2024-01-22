таск1
public class Main {

    public static void main(String[] args) {
        // Примеры вызова функций:
        System.out.println("1. convert(5) ➞ " + convert(5));
        System.out.println("2. fitCalc(15, 1) ➞ " + fitCalc(15, 1));
        System.out.println("3. containers(3, 4, 2) ➞ " + containers(3, 4, 2));
        System.out.println("4. triangleType(5, 5, 5) ➞ " + triangleType(5, 5, 5));
        System.out.println("5. ternaryEvaluation(8, 4) ➞ " + ternaryEvaluation(8, 4));
        System.out.println("6. howManyItems(22, 1.4, 2) ➞ " + howManyItems(22, 1.4, 2));
        System.out.println("7. factorial(3) ➞ " + factorial(3));
        System.out.println("8. gcd(48, 18) ➞ " + gcd(48, 18));
        System.out.println("9. ticketSaler(70, 1500) ➞ " + ticketSaler(70, 1500));
        System.out.println("10. tables(5, 2) ➞ " + tables(5, 2));
    }

    // Задача 1: Преобразование галлонов в литры
    public static double convert(int gallons) {
        // 1 галлон равен приблизительно 3.78541 литрам, поэтому умножаем количество галлонов на этот коэффициент
        return gallons * 3.78541;
    }

    // Задача 2: Расчет калорий, сожженных во время тренировки
    public static int fitCalc(int minutes, int intensity) {
        int caloriesPerMinute;
        // Используем оператор switch для определения калорий, сожженных в минуту в зависимости от интенсивности
        switch (intensity) {
            case 1:
                caloriesPerMinute = 5; // Низкая интенсивность
                break;
            case 2:
                caloriesPerMinute = 10; // Средняя интенсивность
                break;
            case 3:
                caloriesPerMinute = 15; // Высокая интенсивность
                break;
            default:
                caloriesPerMinute = 0; // Если интенсивность не определена, возвращаем 0
        }
        // Умножаем количество минут тренировки на калории, сжигаемые в минуту
        return minutes * caloriesPerMinute;
    }

    // Задача 3: Вычисление общего количества товаров на складе
    public static int containers(int boxes, int bags, int barrels) {
        // Каждая коробка содержит 20 товаров, каждый мешок - 50, каждая бочка - 100
        // Умножаем количество емкостей каждого типа на количество товаров в каждой емкости и суммируем их
        return (boxes * 20) + (bags * 50) + (barrels * 100);
    }

    // Задача 4: Определение типа треугольника
    public static String triangleType(int x, int y, int z) {
        // Проверяем условия, при которых треугольник не существует
        if (x <= 0 || y <= 0 || z <= 0 || x + y <= z || x + z <= y || y + z <= x) {
            return "not a triangle"; // Не является треугольником
        } else if (x == y && y == z) {
            return "equilateral"; // Равносторонний треугольник
        } else if (x == y || y == z || x == z) {
            return "isosceles"; // Равнобедренный треугольник
        } else {
            return "different-sided"; // Разносторонний треугольник
        }
    }

    // Задача 5: Определение большего числа с использованием тернарного оператора
    public static int ternaryEvaluation(int a, int b) {
        // Используем тернарный оператор для выбора большего числа
        return (a > b) ? a : b;
    }


    // Задача 6: Расчет количества пододеяльников, которые можно сшить
    public static int howManyItems(double totalFabricArea, double fabricWidth, double fabricLength) {
        double itemArea = fabricWidth * fabricLength;
        int numberOfItems = (int) (totalFabricArea / (itemArea * 2)); // Умножаем на 2, чтобы учесть требование n * 2
        return numberOfItems;
    }

    // Задача 7: Вычисление факториала числа
    public static int factorial(int n) {
        // Рекурсивная функция для вычисления факториала
        if (n == 0 || n == 1) {
            return 1;
        }
        return n * factorial(n - 1);
    }

    // Задача 8: Вычисление наибольшего общего делителя
    public static int gcd(int a, int b) {
        // Используем алгоритм Евклида для нахождения НОД
        while (b != 0) {
            int temp = b;
            b = a % b;
            a = temp;
        }
        return a;
    }

    // Задача 9: Вычисление выручки от продажи билетов
    public static int ticketSaler(int numTickets, int ticketPrice) {
        int commission = 50; // Фиксированная комиссия
        return numTickets * (ticketPrice - commission);
    }

    // Задача 10: Определение нехватки столов для размещения студентов
    public static int tables(int numStudents, int studentsPerTable) {
        // Определяем, сколько столов необходимо для размещения всех студентов
        int tablesNeeded = numStudents / (studentsPerTable * 2);
        int remainingStudents = numStudents % (studentsPerTable * 2); // Студенты, которые не поместились за столами
        return remainingStudents > 0 ? tablesNeeded + 1 : tablesNeeded;
    }

}


таск 2
import java.util.Arrays;
 class Task2 {
    // Задача 1: Поиск повторяющихся символов в строке
    public static boolean duplicateChars(String str) {
        for (int i = 0; i < str.length(); i++) {
            for (int j = i + 1; j < str.length(); j++) {
                if (str.charAt(i) == str.charAt(j)) {
                    return true; // Если найдены повторяющиеся символы, вернуть true
                }
            }
        }
        return false; // Если нет повторяющихся символов, вернуть false
    }

    // Задача 2: Получение инициалов без пробелов
    public static String getInitials(String fullName) {
        String[] parts = fullName.split(" ");
        StringBuilder initials = new StringBuilder();
        for (String part : parts) {
            initials.append(part.charAt(0));
        }
        return initials.toString();
    }

    // Задача 3: Разница между суммой четных и нечетных чисел в массиве
    public static int differenceEvenOdd(int[] arr) {
        int evenSum = 0;
        int oddSum = 0;
        for (int num : arr) {
            if (num % 2 == 0) {
                evenSum += num;
            } else {
                oddSum += num;
            }
        }
        return evenSum - oddSum;
    }

    // Задача 4: Проверка наличия элемента равного среднему арифметическому
    public static boolean equalToAvg(int[] arr) {
        int sum = 0;
        for (int num : arr) {
            sum += num;
        }
        double average = (double) sum / arr.length;
        for (int num : arr) {
            if (num == average) {
                return true;
            }
        }
        return false;
    }

    // Задача 5: Умножение каждого элемента на его индекс
    public static int[] indexMult(int[] arr) {
        int[] result = new int[arr.length];
        for (int i = 0; i < arr.length; i++) {
            result[i] = arr[i] * i;
        }
        return result;
    }

    // Задача 6: Переворот строки
    public static String reverse(String str) {
        StringBuilder reversed = new StringBuilder();
        for (int i = str.length() - 1; i >= 0; i--) {
            reversed.append(str.charAt(i));
        }
        return reversed.toString();
    }

     // Задача 7: Вычисление числа Трибоначчи
     public static int tribonacci(int n) {
         if (n == 0) return 0;
         if (n <= 2) return 1;
         int[] tribonacci = new int[n + 1];
         tribonacci[0] = 0;
         tribonacci[1] = 0;
         tribonacci[2] = 1;
         for (int i = 3; i <= n; i++) {
             tribonacci[i] = tribonacci[i - 1] + tribonacci[i - 2] + tribonacci[i - 3];
         }
         return tribonacci[n];
     }

     // Задача 8: Генерация квази-хэша
     public static String pseudoHash(int length) {
         StringBuilder pseudoHash = new StringBuilder();
         String characters = "abcdef0123456789";
         for (int i = 0; i < length; i++) {
             int randomIndex = (int) (Math.random() * characters.length());
             pseudoHash.append(characters.charAt(randomIndex));
         }
         return pseudoHash.toString();
     }

    // Задача 9: Поиск слова "help" в строке
    public static String botHelper(String input) {
        input = input.toLowerCase(); // Преобразование к нижнему регистру для поиска
        if (input.contains("help")) {
            return "Calling for a staff member";
        } else {
            return "Keep waiting";
        }
    }

    // Задача 10: Проверка на анаграмму
    public static boolean isAnagram(String str1, String str2) {
        str1 = str1.replaceAll("\\s", "").toLowerCase();
        str2 = str2.replaceAll("\\s", "").toLowerCase();
        if (str1.length() != str2.length()) {
            return false;
        }
        char[] chars1 = str1.toCharArray();
        char[] chars2 = str2.toCharArray();
        Arrays.sort(chars1);
        Arrays.sort(chars2);
        return Arrays.equals(chars1, chars2);
    }

    public static void main(String[] args) {
        // Примеры использования функций
        System.out.println(duplicateChars("donald")); // true
        System.out.println(duplicateChars("orange")); // false

        System.out.println(getInitials("Ryan Gosling")); // "RG"
        System.out.println(getInitials("Barack Obama")); // "BA"

        int[] arr1 = {44, 32, 86, 19};
        System.out.println(differenceEvenOdd(arr1)); // 143

        int[] arr2 = {1, 2, 3, 4, 5};
        System.out.println(equalToAvg(arr2)); // true

        int[] arr3 = {1, 2, 3};
        System.out.println(Arrays.toString(indexMult(arr3))); // [0, 2, 6]

        System.out.println(reverse("Hello World")); // "dlroW olleH"

        System.out.println(tribonacci(7)); // 7

        System.out.println(pseudoHash(5)); // "04bf2"

        System.out.println(botHelper("Hello, I’m under the water, please help me")); // "Calling for a staff member"
        System.out.println(botHelper("Two pepperoni pizzas please")); // "Keep waiting"

        System.out.println(isAnagram("listen", "silent")); // true
        System.out.println(isAnagram("eleven plus two", "twelve plus one")); // true
        System.out.println(isAnagram("hello", "world")); // false
    }
}


таск3
import java.util.ArrayList;
import java.util.Arrays;
import java.util.HashMap;
import java.util.List;
import java.util.Map;

public class Main {
    public static void main(String[] args) {
        // Тестирование всех функций

        // Задача 1
        System.out.println(replaceVowels("apple")); // ➞ "*ppl*"

        // Задача 2
        System.out.println(stringTransform("hello")); // ➞ "heDoubleLo"

        // Задача 3
        System.out.println(doesBlockFit(1, 3, 5, 4, 5)); // ➞ true

        // Задача 4
        System.out.println(numCheck(243)); // ➞ true

        // Задача 5
        System.out.println(countRoots(new int[]{1, -3, 2})); // ➞ 2

        // Задача 6
        String[][] salesData1 = {
                {"Apple", "Shop1", "Shop2", "Shop3", "Shop4"},
                {"Banana", "Shop2", "Shop3", "Shop4"},
                {"Orange", "Shop1", "Shop3", "Shop4"},
                {"Pear", "Shop2", "Shop4"}
        };
        System.out.println(Arrays.toString(salesData(salesData1))); // ➞ ["Apple"]

        String[][] salesData2 = {
                {"Fridge", "Shop2", "Shop3"},
                {"Microwave", "Shop1", "Shop2", "Shop3", "Shop4"},
                {"Laptop", "Shop3", "Shop4"},
                {"Phone", "Shop1", "Shop2", "Shop3", "Shop4"}
        };
        System.out.println(Arrays.toString(salesData(salesData2))); // ➞ ["Microwave", "Phone"]

        // Задача 7
        System.out.println(validSplit("apple eagle egg goat")); // ➞ true

        // Задача 8
        System.out.println(waveForm(new int[]{3, 1, 4, 2, 7, 5})); // ➞ true

        // Задача 9
        System.out.println(commonVowel("Hello world")); // ➞ "o"

        // Задача 10
        int[][] data = {
                {1, 2, 3, 4, 5},
                {6, 7, 8, 9, 10},
                {5, 5, 5, 5, 5},
                {7, 4, 3, 14, 2},
                {1, 0, 11, 10, 1}
        };
        dataScience(data);
        for (int[] row : data) {
            System.out.println(Arrays.toString(row));
        }
    }

    // Задача 1
    public static String replaceVowels(String str) {
        return str.replaceAll("[AEIOUaeiou]", "*");
    }

    // Задача 2
    public static String stringTransform(String str) {
        StringBuilder result = new StringBuilder();
        for (int i = 0; i < str.length(); i++) {
            char currentChar = str.charAt(i);
            result.append(currentChar);
            if (i < str.length() - 1 && currentChar == str.charAt(i + 1)) {
                result.append("Double");
            }
        }
        return result.toString();
    }

    // Задача 3
    public static boolean doesBlockFit(int a, int b, int c, int w, int h) {
        int[] block = {a, b, c};
        Arrays.sort(block);
        int[] hole = {w, h};
        Arrays.sort(hole);
        return block[0] <= hole[0] && block[1] <= hole[1];
    }

    // Задача 4
    public static boolean numCheck(int num) {
        int sumOfSquares = 0;
        int temp = num;
        while (temp > 0) {
            int digit = temp % 10;
            sumOfSquares += digit * digit;
            temp /= 10;
        }
        return num % 2 == sumOfSquares % 2;
    }

    // Задача 5
    public static int countRoots(int[] coefficients) {
        int count = 0;
        for (int i = 0; i < coefficients.length - 2; i++) {
            if (coefficients[i] < coefficients[i + 1] && coefficients[i + 1] > coefficients[i + 2]) {
                count++;
            }
            if (coefficients[i] > coefficients[i + 1] && coefficients[i + 1] < coefficients[i + 2]) {
                count++;
            }
        }
        return count;
    }

    // Задача 6
    public static String[] salesData(String[][] data) {
        Map<String, List<String>> productToShops = new HashMap<>();
        for (String[] row : data) {
            String product = row[0];
            for (int i = 1; i < row.length; i++) {
                String shop = row[i];
                productToShops.computeIfAbsent(product, k -> new ArrayList<>()).add(shop);
            }
        }
        List<String> result = new ArrayList<>();
        for (Map.Entry<String, List<String>> entry : productToShops.entrySet()) {
            if (entry.getValue().size() == data.length - 1) {
                result.add(entry.getKey());
            }
        }
        return result.toArray(new String[0]);
    }

    // Задача 7
    public static boolean validSplit(String sentence) {
        String[] words = sentence.split(" ");
        if (words.length < 2) {
            return false;
        }
        for (int i = 1; i < words.length; i++) {
            if (words[i].charAt(0) != words[i - 1].charAt(words[i - 1].length() - 1)) {
                return false;
            }
        }
        return true;
    }

    // Задача 8
    public static boolean waveForm(int[] arr) {
        if (arr.length < 2) {
            return false;
        }
        boolean increasing = arr[0] < arr[1];
        for (int i = 1; i < arr.length - 1; i++) {
            if (increasing) {
                if (arr[i] >= arr[i + 1]) {
                    return false;
                }
            } else {
                if (arr[i] <= arr[i + 1]) {
                    return false;
                }
            }
            increasing = !increasing;
        }
        return true;
    }

    // Задача 9
    public static String commonVowel(String sentence) {
        String vowels = "AEIOUaeiou";
        Map<Character, Integer> vowelCount = new HashMap<>();
        for (char c : sentence.toCharArray()) {
            if (vowels.contains(String.valueOf(c))) {
                vowelCount.put(c, vowelCount.getOrDefault(c, 0) + 1);
            }
        }
        char mostCommonVowel = ' ';
        int maxCount = 0;
        for (Map.Entry<Character, Integer> entry : vowelCount.entrySet()) {
            if (entry.getValue() > maxCount) {
                maxCount = entry.getValue();
                mostCommonVowel = entry.getKey();
            }
        }
        return String.valueOf(mostCommonVowel);
    }

    // Задача 10
    public static void dataScience(int[][] data) {
        int n = data.length;
        int m = data[0].length;
        int[] colSums = new int[m];

        // Вычисляем сумму по столбцам
        for (int i = 0; i < m; i++) {
            for (int j = 0; j < n; j++) {
                colSums[i] += data[j][i];
            }
        }

        // Заменяем каждый n-ый элемент n-го массива на среднее арифметическое элементов столбца
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < m; j++) {
                if ((i + 1) % n == 0) {
                    data[i][j] = colSums[j] / n;
                }
            }
        }
    }
}


таск 4
import java.util.*;

public class Main {
    public static void main(String[] args) {
        // Вызов функций с примерами данных
        System.out.println("1. " + nonRepeatable("abracadabra")); // ➞ " abrcd"
        System.out.println("2. " + generateBrackets(3)); // ➞ ["((()))", "(()())", "(())()", "()(())", "()()()"]
        System.out.println("3. " + binarySystem(4)); // ➞ ["0101", "0110", "0111", "1010", "1011", "1101", "1110", "1111"]
        System.out.println("4. " + alphabeticRow("abcdjuwx")); // ➞ "abcd"
        System.out.println("5. " + countAndSort("aaabbcdd")); // ➞ "c1b2d2a3"
        System.out.println("6. " + convertToNum("eight")); // ➞ 8
        System.out.println("7. " + uniqueSubstring("123412324")); // ➞ "1234"
        System.out.println("8. " + shortestWay(new int[][]{{1, 3, 1}, {1, 5, 1}, {4, 2, 1}})); // ➞ 7
        System.out.println("9. " + numericOrder("t3o the5m 1One all6 r4ule ri2ng")); // ➞ " One ring to rule them all"
        System.out.println("10. " + switchNums(519, 723)); // ➞ 953
    }

    // Задание 1
    public static String nonRepeatable(String s) {
        if (s.isEmpty()) {
            return "";
        }
        char firstChar = s.charAt(0);
        String rest = nonRepeatable(s.substring(1));
        if (rest.contains(String.valueOf(firstChar))) {
            return rest;
        } else {
            return firstChar + rest;
        }
    }

    // Задание 2
    public static List<String> generateBrackets(int n) {
        List<String> result = new ArrayList<>();
        generateBracketsHelper(result, "", n, n);
        return result;
    }

    private static void generateBracketsHelper(List<String> result, String current, int open, int close) {
        if (open == 0 && close == 0) {
            result.add(current);
        }
        if (open > 0) {
            generateBracketsHelper(result, current + "(", open - 1, close);
        }
        if (close > open) {
            generateBracketsHelper(result, current + ")", open, close - 1);
        }
    }

    // Задание 3
    public static List<String> binarySystem(int n) {
        List<String> result = new ArrayList<>();
        binarySystemHelper(result, "", n);
        return result;
    }

    private static void binarySystemHelper(List<String> result, String current, int n) {
        if (current.length() == n) {
            result.add(current);
            return;
        }
        if (current.isEmpty() || current.charAt(current.length() - 1) == '1') {
            binarySystemHelper(result, current + "0", n);
        }
        binarySystemHelper(result, current + "1", n);
    }

    // Задание 4
    public static String alphabeticRow(String s) {
        String longestRow = "";
        String currentRow = "" + s.charAt(0);
        for (int i = 1; i < s.length(); i++) {
            if (s.charAt(i) - s.charAt(i - 1) == 1) {
                currentRow += s.charAt(i);
            } else {
                if (currentRow.length() > longestRow.length()) {
                    longestRow = currentRow;
                }
                currentRow = "" + s.charAt(i);
            }
        }
        if (currentRow.length() > longestRow.length()) {
            longestRow = currentRow;
        }
        return longestRow;
    }

    // Задание 5
    public static String countAndSort(String s) {
        Map<Character, Integer> charCount = new HashMap<>();
        for (char c : s.toCharArray()) {
            charCount.put(c, charCount.getOrDefault(c, 0) + 1);
        }
        List<Map.Entry<Character, Integer>> sortedEntries = new ArrayList<>(charCount.entrySet());
        sortedEntries.sort(Comparator.comparingInt(Map.Entry::getValue));
        StringBuilder result = new StringBuilder();
        for (Map.Entry<Character, Integer> entry : sortedEntries) {
            result.append(entry.getKey()).append(entry.getValue());
        }
        return result.toString();
    }

    // Задание 6
    public static int convertToNum(String s) {
        Map<String, Integer> wordsToNumbers = new HashMap<>();
        wordsToNumbers.put("one", 1);
        wordsToNumbers.put("two", 2);
        wordsToNumbers.put("three", 3);
        wordsToNumbers.put("four", 4);
        wordsToNumbers.put("five", 5);
        wordsToNumbers.put("six", 6);
        wordsToNumbers.put("seven", 7);
        wordsToNumbers.put("eight", 8);
        wordsToNumbers.put("nine", 9);
        wordsToNumbers.put("ten", 10);
        String[] words = s.split(" ");
        int result = 0;
        for (String word : words) {
            if (wordsToNumbers.containsKey(word)) {
                result += wordsToNumbers.get(word);
            }
        }
        return result;
    }

    // Задание 7
    public static String uniqueSubstring(String s) {
        Set<Character> uniqueChars = new HashSet<>();
        String longestSubstring = "";
        String currentSubstring = "";
        for (int i = 0; i < s.length(); i++) {
            char c = s.charAt(i);
            if (uniqueChars.contains(c)) {
                while (currentSubstring.charAt(0) != c) {
                    uniqueChars.remove(currentSubstring.charAt(0));
                    currentSubstring = currentSubstring.substring(1);
                }
                currentSubstring = currentSubstring.substring(1) + c;
            } else {
                uniqueChars.add(c);
                currentSubstring += c;
                if (currentSubstring.length() > longestSubstring.length()) {
                    longestSubstring = currentSubstring;
                }
            }
        }
        return longestSubstring;
    }

    // Задание 8
    public static int shortestWay(int[][] grid) {
        int m = grid.length;
        int n = grid[0].length;
        int[][] dp = new int[m][n];
        dp[0][0] = grid[0][0];

        for (int i = 1; i < m; i++) {
            dp[i][0] = dp[i - 1][0] + grid[i][0];
        }

        for (int j = 1; j < n; j++) {
            dp[0][j] = dp[0][j - 1] + grid[0][j];
        }

        for (int i = 1; i < m; i++) {
            for (int j = 1; j < n; j++) {
                dp[i][j] = Math.min(dp[i - 1][j], dp[i][j - 1]) + grid[i][j];
            }
        }

        return dp[m - 1][n - 1];
    }

    // Задание 9
    public static String numericOrder(String s) {
        String[] words = s.split(" ");
        Map<Integer, String> orderToWords = new TreeMap<>();
        for (String word : words) {
            for (char c : word.toCharArray()) {
                if (Character.isDigit(c)) {
                    int order = Character.getNumericValue(c);
                    orderToWords.put(order, word);
                    break;
                }
            }
        }
        StringBuilder result = new StringBuilder();
        for (String word : orderToWords.values()) {
            result.append(word).append(" ");
        }
        return result.toString().trim();
    }

    // Задание 10
    public static int switchNums(int num1, int num2) {
        char[] num1Digits = String.valueOf(num1).toCharArray();
        char[] num2Digits = String.valueOf(num2).toCharArray();
        Arrays.sort(num2Digits);
        StringBuilder result = new StringBuilder();
        int num1Index = 0;
        int num2Index = 0;

        while (num1Index < num1Digits.length && num2Index < num2Digits.length) {
            if (num1Digits[num1Index] <= num2Digits[num2Index]) {
                result.append(num1Digits[num1Index]);
                num1Index++;
            } else {
                result.append(num2Digits[num2Index]);
                num2Index++;
            }
        }

        while (num1Index < num1Digits.length) {
            result.append(num1Digits[num1Index]);
            num1Index++;
        }

        while (num2Index < num2Digits.length) {
            result.append(num2Digits[num2Index]);
            num2Index++;
        }

        return Integer.parseInt(result.toString());
    }
}

таск5
