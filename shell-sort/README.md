# shell-sort

### Algorithm Description
- Find all the gap we will be using to do the insertion sort on
- Divide the array into small section for each of the gap
- Do an insertion sort for each of the sections to sort them in order
- Once all sections are sorted, we reduce the gap and redo step 2–3

### Properties
- Space Complexity: O(1)
- Time Complexity: O(nlog n), O(nlog n), O(n2) for Best, Average, Worst cases respectively.
- Stable: No

---

### Shell Sort in JavaScript

```
shellSort(arr) {
	let n = arr.length;

	for (let gap = Math.floor(n/2); gap > 0; gap = Math.floor(gap/2))	{
		for (let i = gap; i < n; i += 1)  {
			let temp = arr[i];
			
			let j;
			for (j = i; j >= gap && arr[j-gap] > temp; j-=gap)  {
				arr[j] = arr[j-gap];
			}

			arr[j] = temp;
		}
	}

	return arr;
}
```
### GIF Demo

#### Demo 1

<img src="https://github.com/AlanTeeWeiLoon/10BestSortingAlgorithms/blob/main/shell-sort/public/Images/Shell-Sort.gif" />

---

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

