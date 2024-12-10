### README: Реализация алгоритмов сортировки в `Sorter<T>`  

---

### Описание проекта  

Класс `Sorter<T>` реализует несколько популярных алгоритмов сортировки, которые можно применять к последовательностям элементов (обобщенный тип `T`). Все алгоритмы используют пользовательскую функцию сравнения `cmp` для сортировки, что позволяет контролировать порядок элементов.  

---

### Алгоритмы сортировки  

#### 1. **QuickSort** (Быстрая сортировка)  
**Описание**:  
Быстрая сортировка — это алгоритм "разделяй и властвуй", который разбивает массив на две части относительно опорного элемента (pivot). Все элементы меньше `pivot` помещаются в левую часть, а больше — в правую. Процесс рекурсивно повторяется для обеих частей.  

**Методы:**  
- `QuickSort(int low, int high, Sequence<T>* sequence, int (*cmp)(const T&, const T&))` — рекурсивно сортирует подмассивы.  
- `Partition(int low, int high, Sequence<T>* sequence, int (*cmp)(const T&, const T&))` — выбирает опорный элемент и выполняет перестановку элементов.  

**Временная сложность**:  
- Средняя: `O(n log n)`  
- Худшая: `O(n^2)`  

---

#### 2. **HeapSort** (Пирамидальная сортировка)  
**Описание**:  
Пирамидальная сортировка использует бинарную кучу (heap), которая поддерживает порядок элементов. На первом этапе массив преобразуется в кучу, после чего на каждом шаге наибольший элемент перемещается в конец, а структура кучи восстанавливается.  

**Методы:**  
- `SiftDown(int n, int i, Sequence<T>* sequence, int (*cmp)(const T&, const T&))` — восстанавливает свойства кучи.  

**Временная сложность**:  
- `O(n log n)` во всех случаях.  

---

#### 3. **MergeSort** (Сортировка слиянием)  
**Описание**:  
Алгоритм "разделяй и властвуй". Исходный массив рекурсивно делится на две половины, которые сортируются и объединяются обратно в отсортированный массив.  

**Методы:**  
- `MergeSort(int low, int high, Sequence<T>* sequence, int (*cmp)(const T&, const T&))` — рекурсивно сортирует части.  
- `Merge(int low, int middle, int high, Sequence<T>* sequence, int (*cmp)(const T&, const T&))` — выполняет слияние двух отсортированных частей.  

**Временная сложность**:  
- `O(n log n)` во всех случаях.  

---

#### 4. **ShakerSort** (Шейкерная сортировка)  
**Описание**:  
Шейкерная сортировка — это двунаправленный вариант пузырьковой сортировки. Алгоритм выполняет проход по массиву в обоих направлениях, что ускоряет сортировку при частично упорядоченных данных.  

**Методы:**  
- `ShakerSorting(Sequence<T>* sequence, int (*cmp)(const T&, const T&))` — основной метод шейкерной сортировки.  

**Временная сложность**:  
- Средняя и худшая: `O(n^2)`  

---

#### 5. **BubbleSort** (Пузырьковая сортировка)  
**Описание**:  
Простой алгоритм сортировки, который последовательно сравнивает пары элементов и меняет их местами, если они расположены в неправильном порядке. Процесс повторяется до тех пор, пока массив не будет отсортирован.  

**Методы:**  
- `BubbleSorting(Sequence<T>* sequence, int (*cmp)(const T&, const T&))` — выполняет пузырьковую сортировку.  

**Временная сложность**:  
- Средняя и худшая: `O(n^2)`  

---


### Временные сложности алгоритмов  

| Алгоритм       | Лучший случай | Средний случай | Худший случай |  
|----------------|--------------|---------------|---------------|  
| QuickSort      | `O(n log n)` | `O(n log n)`  | `O(n^2)`      |  
| HeapSort       | `O(n log n)` | `O(n log n)`  | `O(n log n)`  |  
| MergeSort      | `O(n log n)` | `O(n log n)`  | `O(n log n)`  |  
| ShakerSort     | `O(n)`       | `O(n^2)`      | `O(n^2)`      |  
| BubbleSort     | `O(n)`       | `O(n^2)`      | `O(n^2)`      |  
