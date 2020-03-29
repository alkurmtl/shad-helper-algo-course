Для тех, кто хорошо понял материал в посте, предлагаю задания посложнее.

Для каждого кода надо оценить асимптотику, а также написать максимальный порядок параметров, при которых выполнение данного кода зайдет в 1 сек.

	1. Сортировка пузырьком.
	
		for (int i = 0; i < n - 1; ++i) {
			for (int j = 0; j < n - i; ++j) {
				if (a[j] > a[j+1]) {
					int tmp = a[j];
					a[j] = a[j+1];
					a[j+1] = tmp;
				}
			}
		}
		
	2. Бинарный поиск индекса элемента со значением value в отсортированном массиве.
		
		int index = -1;
		int left = 0, right = n - 1;
		while (left <= right) {
			int mid = (left + right) / 2;
			
			if (a[mid] < value) {
				left = mid + 1;
			} else if (a[mid] > value) {
				right = mid - 1;
			} else {
				index = mid;
				break;
			}
		}
		print(index);
		
	3. Вложенные циклы.
		
		for (int i = 0, j = 0; i < n; ++i) {
			while (j < n && a[i] > a[j]) {
				++j;
			}
			if (a[i] > a[j]) {
				print(a[j] + " " + a[i]);
			}
		}
			
	4. Странная функция.
	
		void f(int mask, int index, int length) {
			if (index == length) {
				print(mask);
			} else {
				f(mask * 2, index + 1, length);
				f(mask * 2 + 1, index + 1, length);
			}
		}
		void main() {
			f(0, 0, N);
		}
	
	5. Нахождение всех делителей числа X (предлагаю привести наиболее оптимальный с вашей точки зрения код и оценить его).
	
	6. Еще раз вложенные циклы.
	
		for (int i = 1; i <= n; ++i) {
			for (int j = i; j <= n; j += i) {
				counts[j]++;
			}
		}