# Writing Test Week 2
## **Javascipt Dasar**
### **JS Dasar Scope**
- Scope adalah flow data variabel, menentukan suatu variabel dapat diakses pada scope tertentu atau tidak
- Blocks adalah kode yang didalam curly braces seperti "{}"
- Conditional, function dan looping menggunakan Blocks
- Global Scope adalah variabel yang kita buat namun bisa diakses dimanapun dalam suatu file dengan cara dideklarasikan diluar blocks
- Local Scope adalah variabel yang kita buat dan dideklarasikan dalam blocks, blocks yaitu function, conditional dan looping beda dengan Global Scope yang berdiri sendiri
- Jadi Local Scope hanya bisa diakses dalam blocks saja.
- dibawah ini contoh sederhana variabel "myName dideklarasikan secara Global Scope

```
Let myName = 'Raisha'; // global scope karena diluar fungsi
function greeting(){ // ini local scope
    return myName; // Raisha
}

console.log(myName); // Raisha
```
- Contoh Sederhana Local Scope

```
function greeting(){ // ini local scope jadi hanya dapat diakses lewat function
    let myName = 'Raisha';
    return myName; // Raisha
}

console.log(greeting()) // Raisha
console.log(myName); // error karena tidak dapat diakses
```

### **JS Dasar Function**
- Function adalah sebuah blok kode dalam sebuah grup untuk menyelesaikan 1 fitur sehingga pada saat kita membutuhkan fitur tersebut kita bisa menggunakannya lagi
- Disini terdapat sintaks js function :

```
function name(parameter1, parameter2, parameter3) {
  // code to be executed
}
```

- contoh sederhana function :
```
let x = myFunction(4, 3);   // fungsi dipanggil, return value akan berakhir di x

function myFunction(a, b) { // argumen function si a dan b
  return a * b;             // fungsi mengembalikan a dan b
}
```

### **Default Parameters**
- parameter ini digunakan untuk memberikan nilai awal pada parameter function
- parameter ini dapat menjaga function agar tidak error saat dipanggil tanpa argumen

```
function greetOnWebsite(name =  'Stranger'){
    return 'Hello ' + name;
}

console.log(greetOnWebsite('David')); // hasilnya 'Hello David'
console.log(greetOnWebsite()); // hasilnya 'Hello Stranger'
```

### **Arrow Function**
- Cara lain menuliskan function, fitur terbaru ES6 pada javascript

```
const greeting = () => { // contoh 1
    return 'Halo gais';
}

const perkalian = (a, b) => { // contoh 2
    return a + b;
}
```

### **Data Type Built in Prototype & Method**
- Tipe data javascript terdiri dari tipe data primitive yaitu:
    1. Boolean, true and false
    2. Null
    3. Undefined, nilainya masih belum ditentukan
    4. Number, Number dan BigInt jadi NaN
    5. BigInt, contoh nya :

        ```
        // BigInt
        const x = BigInt(Number.MAX_SAFE_INTEGER); // 9007199254740991n
        x + 1n === x + 2n; // false because 9007199254740992n and 9007199254740993n are unequal

        // Number
        Number.MAX_SAFE_INTEGER + 1 === Number.MAX_SAFE_INTEGER + 2; // true because both are 9007199254740992
        ```

    6. String, substring() dan concat(), contoh string sederhana :

        ```
        const string1 = "A string primitive";
        const string2 = 'Also a string primitive';
        const string3 = `Yet another string primitive`;
        ```
    7. Simbol

- Ada juga Math yaitu objek yang memiliki properti dan method untuk fungsi matematika dan konstanta. contohnya :
    1. Math.PI, nilai pi dari lingkaran
    2. Math.SQRT1/2, akar kuadrat setengah dari
    3. Math.SQRT2, akar kuadrat 2 dari

### **DOM**
- DOM bukan bagian dari JavaScript melainkan browser (Web API)
- Jika script yang diunduh ukurannya besar kita dapat :
    1. Taruh tag <script> eksternal sebelum tag penutup </body>
    2. Taruh tag <script> sedini mungkin dan gunakan atribut async
    3. Untuk script yang bergantung pada DOM, taruh tag <script> sedini mungkin, dan gunakan atribut defer

- Memanipulasi Element HTML :
    1. Mencari Element HTML
    2. Mengubah Konten Element bisa dengan Element.textContent yang mengubah teks dalam sebuah element dan Element.innerHTML digunakan untuk mengubah konten HTML dalam sebuah element
    3. Mengubah Atribut Element
    4.  Membuat Element

### **Interaksi User atau Events**
- User experience bersifat dua arah yaitu menampilkan element HTML dan halaman web juga dapat berinteraksi dengan user.
- Menangkap interaksi user itu bisa dengan Element.addEventListener(“event”), contoh :
```
// cari dulu kedua element tersebut berdasarkan id-nya

const input = document.getElementById(“user-input”)
const button = document.getElementById(“alert-button”)

// baru tambahkan event listener
button.addEventListener(“click”, function() {
	alert(input.value)
})

// atau
button.onclick = function() { alert(input.value) }
```

- EventListener - Blur
```
// cari dulu element tersebut berdasarkan id-nya

const input = document.getElementById(“username”)

// tambahkan event listener
input.addEventListener(“blur”, () => {
	if(input.value.length < 6) alert(“Panjang username minimal 6”)
})
```

- EventListener - Form Submission
Misalkan kita mempunyai element beberapa input dalam sebuah form <input name=”email /> dan <input type=”password” name=”password” />.

```
const form = document.getElementById(“form”)

form.addEventListener(“submit”, function(event) {
	// cegah page refresh
	event.preventDefault()

	const formData = new FormData(form)
	const values = Object.fromEntries(formData) // { email: ... }
})
```


# Writing-Test-Week-2
