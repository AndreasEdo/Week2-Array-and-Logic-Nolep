# Logic Challenge | Part 2

***DISINI  SOALNYA BELUM PAKE ARRAY, HANYA LOGIC***

`jaman dahulu kala gua struggle di palindrome angka - Harkon 2020`

siap siap merasakan ***PAHITNYA LOOPING***

## Soal 1
```js
/*
Diberikan sebuah function palindrome(kata) yang menerima satu parameter. Function tersebut akan mengembalikan nilai true jika kata merupakan palindrome, dan false jika bukan. Kata palindrome adalah sebuah kata yang jika dibalik, tetap sama. Contoh, 'katak' dibalik tetaplah 'katak'.
*/

function palindrome(kata) {
    let kataDibalik = '';
    for(let i=kata.length-1;i>=0;i--) {
      kataDibalik += kata[i];
    }
    if(kataDibalik === kata){
      return `true`;
    }
    return `false`;
}

// TEST CASES
console.log(palindrome('katak')); // true
console.log(palindrome('blanket')); // false
console.log(palindrome('civic')); // true
console.log(palindrome('kasur rusak')); // true
console.log(palindrome('mister')); // false
```

## Soal 2
```js
/*
Diberikan sebuah function angkaPalindrome(angka) yang menerima satu parameter angka. Function akan me-return angka selanjutnya yang mengandung nilai angka palindrome. Contoh, jika angka adalah 27, maka function akan me-return nilai 33 karena angka 33 adalah angka palindrom. Jika angka dari awal sudah merupakan palindrome, maka function harus mencari angka selanjutnya yang palindrome. Contoh, jika angka adalah 8, walaupun dia sudah palindrome, harus mencari angka selanjutnya yang palindrome, yaitu 9.

note kenapa angka 8 adalah palindrome? karena angka 8 dibalik tetep 8 wkwkw
note kenapa angka 343 adalah palindrome? karena angka 343 dibalik tetep 343 eaaaa
*/

function angkaPalindrome(num) {
    let numString = '';
    let reverseNum = '';
    do {
        num++;
        numString = num.toString();
        reverseNum = '';

        for (let i = numString.length - 1; i >= 0; i--) {
            reverseNum += numString[i];
        }

    } while (numString !== reverseNum); 

    return num;
}

// TEST CASES
console.log(angkaPalindrome(8)); // 9
console.log(angkaPalindrome(10)); // 11
console.log(angkaPalindrome(117)); // 121
console.log(angkaPalindrome(175)); // 181
console.log(angkaPalindrome(1000)); // 1001
```

## Soal 3
```js
function hitungJumlahKata(kalimat) {
    let count=0;
    for(let i=0;i<kalimat.length;i++){
        if(kalimat[i] === ' '){
            count++;
        }
    }
    count++;
    return count;
  }
  
// TEST CASES
console.log(hitungJumlahKata('I have a dream')); // 4
console.log(hitungJumlahKata('Never eat shredded wheat or cake')); // 6
console.log(hitungJumlahKata('A song to sing')); // 4
console.log(hitungJumlahKata('I')); // 1
console.log(hitungJumlahKata('I believe I can code')); // 5
```

## Soal 4
```js
function pasanganTerbesar(num) {
    let num1 = 1;
    let num2 = -1;
    let numString = num.toString();
    let tempBiggest = 0;
    for(let i=0;i<numString.length;i++){
        if(tempBiggest < numString.slice(num2, num1)){
            tempBiggest = numString.slice(num2,num1);
        }
        num1++;
        num2++;
    }
    return tempBiggest;
}
  
  // TEST CASES
console.log(pasanganTerbesar(641573)); // 73
console.log(pasanganTerbesar(12783456)); // 83
console.log(pasanganTerbesar(910233)); // 91
console.log(pasanganTerbesar(71856421)); // 85
console.log(pasanganTerbesar(79918293)); // 99
```

TIPS buat soal no 4: bikin variabel yang ngebikin tipe data number ke string biar bisa di loop