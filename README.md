# Fruits into baskets


```java
public class App {

	public static void main(String[] args) {
		System.out.println(totalFruit(new int[] { 3, 3, 2 }));
	}

	private static int totalFruit(int[] trees) {
		int last_fruit = -1;
		int second_last_fruit = -1;

		int current_max = 0;
		int global_max = 0;

		int last_fruit_count = 0;

		for (int current_fruit : trees) {
			if (current_fruit == last_fruit || current_fruit == second_last_fruit) {
				current_max += 1;
			} else {
				current_max = last_fruit_count + 1;
			}

			if (current_fruit == last_fruit) {
				last_fruit_count += 1;
			} else {
				last_fruit_count = 1;
			}

			if (current_fruit != last_fruit) {
				second_last_fruit = last_fruit;
				last_fruit = current_fruit;
			}

			global_max = Math.max(global_max, current_max);
		}
		return global_max;
	}
}

```

Above implementation have runtime complexity of O(n) and space complexity of O(1)
```
Runtime Complexity = O(n)
Space Complexity   = O(1)
```
