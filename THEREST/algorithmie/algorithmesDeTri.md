# Les algorithmes de tri

Des algorithmes qui servent à trier des tableaux.

- ## Algorithme de tri simple

    ``` processing
    int [] arr = {3, 9, 7, 1, 6, 2, 8, 4};

    void setup() {
        for (int i = 0; i < arr.length; i++) {
            for (int j = 0; j < arr.length; j++) {
                int temp;

                if (arr[j] > arr [i]) {
                    temp = arr[i];
                    arr[i] = arr[j];
                    arr[j] = temp;
                }
            }
        }
        println(arr);
    }
    ```


- ## Algorithme de tri par insertion

    ``` processing
    int [] arr = {3, 9, 7, 12, 1, 6, 2, 8, 4, 5, 10, 15, -5};

    void triInsertion(int[] arr) {
    
        for (int i = 1; i < arr.length; i++) {
            
            int temp = arr[i];
            int j = i;
            
            while(j > 0 && arr[j-1] > temp) {
                arr[j] = arr[j-1];
                j = j-1;
            }
            arr[j] = temp;
        }
        println(arr);
    }

    void setup() {
        triInsertion(arr);
    }
    ```

    [Algorithme de tri par insertion](http://lwh.free.fr/pages/algo/tri/tri_insertion.html)

- ## Algorithme de tri par sélection

    ``` processing
    int [] arr = {3, 9, 4, 7, 12, 1, 6, 2, 8, 4, 5, 10, 15, -5};

    void triSelection(int[] arr) {
        for (int i = 0; i < arr.length; i++) {
            
            int min = i;
            int temp = arr[i];
            for (int j = i; j < arr.length; j++) {
                if (arr[j] < arr[min]) {
                    min = j;
                }
            }
            arr[i] = arr[min];
            arr[min] = temp;
        }
        println(arr);
    }

    void setup() {
        triSelection(arr);
    }
    ```

    [Algorithme de tri par sélection](http://lwh.free.fr/pages/algo/tri/tri_selection.html)


- ## Algorithme de tri a bulle

    ``` processing
    int [] arr = {3, 9, 4, 7, 12, 1, 6, 2, 8, 4, 5, 10, 15, -5};

    void triBulle(int[] arr) {
    
        boolean permut = true;
    
        while (permut) {
            permut = false;

            for (int i = 0; i < arr.length-1; i++) {
                int temp = arr[i];

                if (arr[i] > arr[i+1]) {
                    permut = true;
                    arr[i] = arr[i+1];
                    arr[i+1] = temp;
                }
            }
        }
        println(arr);
    }

    void setup() {
        triBulle(arr);
    }
    ```

    [Algorithme de tri a bulle](http://lwh.free.fr/pages/algo/tri/tri_bulle.html)


- ## Algorithme de tri de shell

    ``` processing
    int [] arr = {3, 9, 7, 12, 1, 6, 2, 8, 4, 5, 10, 15, -5};
    int temp;

    void triInsertion(int[] arr) {
    
        int n = arr.length;
        int gap = 0;
        while(gap < n) {
            gap = 3*gap+1;
        }
        
        while(gap != 0) {
            gap = gap/3;
            
            for (int i = gap; i < n; i++) {
                temp = arr[i];
                int j = i;
                
                while(j > gap-1 && arr[j-gap] > temp) {
                    arr[j] = arr[j-gap];
                    j = j-gap;
                }
                arr[j] = temp;
            }
            println(arr);
        }
    }
    void setup() {
        triInsertion(arr);
    }
    ```

    [Algorithme de tri de shell](http://lwh.free.fr/pages/algo/tri/tri_shell.html)

    [Vidéo explicative](https://www.youtube.com/watch?v=ddeLSDsYVp8)

    