---
🚀 CPPS - Ngôn Ngữ Lập Trình CP+* (C-Plus-Plus-Star)

https://img.shields.io/badge/version-2.0.0-blue
https://img.shields.io/badge/python-3.8%2B-green
https://img.shields.io/badge/license-MIT-orange

CPPS là trình thông dịch cho ngôn ngữ CP+* (C-Plus-Plus-Star) - một ngôn ngữ lập trình hiện đại, kết hợp sức mạnh của C++, sự thanh lịch của Python và tính an toàn của Rust.
---

📖 Giới Thiệu

CP+* (C-Plus-Plus-Star) là ngôn ngữ lập trình đa năng với:

· Cú pháp độc đáo - Các toán tử đặc biệt giúp code ngắn gọn
· Hệ thống Ownership - Quản lý bộ nhớ an toàn (own, share, borrow)
· OOP đầy đủ - Class, struct, trait, impl, inheritance
· Pattern Matching - Linh hoạt và mạnh mẽ
· Concurrency - Goroutines và Channels
· REPL - Tương tác trực tiếp
· Reflection & Macros - Metaprogramming

---

🎯 Cú Pháp Đặc Biệt

Ký hiệu Ý nghĩa Ví dụ
:= Biến bất biến x := 42
:: mut Biến mutable y :: mut int = 0
++ Định nghĩa hàm ++ add <~ (a, b) ** { ... }
<~ Mũi tên tham số ++ fn <~ (p: int) ** { ... }
-> Kiểu trả về -> int
** Mở đầu block ** { body }
?? If ?? x > 0 ** { ... }
<> For-each <> i :: list ** { ... }
~> In ra ~> io::println("Hello!")
<- Return <- value
!! Panic !! "error"
!> Break !>
!>> Continue !>>
?~ Pattern match ?~ value { ... }
@ Self @.field
:: Method call obj:method()
@@ Annotation @@override
-- Comment -- comment
--[[ ]] Multi-line comment --[[ comment ]]
own<T> Ownership own<int> x := 42
share<T> Shared ref share<string> name
borrow<T> Borrow borrow<int> ptr
go Goroutine go my_function()
'a Lifetime 'static
---

💻 Ví Dụ Cơ Bản

Hello World

```cpps
++ main <~ () -> int ** {
    name := "World"
    ~> io::println("Hello, {}!", name)
    <- 0
}
```

Biến và Kiểu Dữ Liệu

```cpps
-- Immutable
x := 42
message := "CP+* is awesome!"

-- Mutable
counter :: mut int = 0
score :: mut float = 95.5

-- Ownership
own<string> owned_name := "Rust style!"
share<int> shared_value := 100
borrow<float> borrowed := 3.14
```

Hàm và Luồng Điều Khiển

```cpps
++ double <~ (n: int) -> int ** {
    <- n * 2
}

?? x > 0 ** {
    ~> io::println("Positive")
} -- elif x < 0 ** {
    ~> io::println("Negative")
} -- else ** {
    ~> io::println("Zero")
}

<> item :: items ** {
    ~> io::println("Item: {}", item)
}

count :: mut int = 0
while count < 5 ** {
    ~> io::println("Count: {}", count)
    count += 1
}

?~ score {
    90..=100 => { ~> io::println("Excelente!") },
    70..89   => { ~> io::println("Good") },
    _        => { ~> io::println("Keep trying") }
}
```

Class và OOP

```cpps
class Animal -> {
    name :: mut string = ""
    
    ++ new <~ (n: string) ** {
        @.name = n
    }
    
    ++ speak <~ () -> void ** {
        ~> io::println("{} says: ...", @.name)
    }
}

class Dog : Animal -> {
    breed :: string = "Unknown"
    
    ++ new <~ (n: string, b: string) ** {
        @.name = n
        @.breed = b
    }
    
    @@override
    ++ speak <~ () -> void ** {
        ~> io::println("{} says: Woof!", @.name)
    }
}

dog := Dog::new("Rex", "German Shepherd")
dog:speak()
```

Concurrency

```cpps
ch := Channel::new(10)
go process_data(ch)

++ process_data <~ (ch: Channel) ** {
    data := ch:recv()
    ~> io::println("Received: {}", data)
}

ch:send(42)
```

---

🛠️ Cài Đặt và Sử Dụng

Yêu Cầu

· Python 3.8 trở lên

Cài Đặt

```bash
# Clone repository
git clone https://github.com/Mark-Vem/CPPS.git
cd cpps-native

# Chạy chương trình CP+*
cpps hello.cpps
```

CLI Commands

```bash
# Chạy file
python cpps.py file.cpps

# Verbose mode
python cpps.py file.cpps --verbose

# Inline code
python cpps.py -e 'x := 42; ~> io::println("x = {}", x)'

# Hiển thị AST
python cpps.py --ast file.cpps

# Hiển thị tokens
python cpps.py --tokens file.cpps

# Khởi động REPL
python cpps.py --repl

# Hiện version
python cpps.py --version
```

REPL Commands

Lệnh Chức năng
:help, :h Trợ giúp
:quit, :q Thoát
:clear, :c Xóa màn hình
:reset Reset interpreter
:env Hiển thị biến
:ast <code> Hiện AST
:tokens <code> Hiện tokens
:time <code> Đo thời gian
:type <expr> Hiển thị kiểu
:load <file> Load file .cpps

---

📂 Cấu Trúc Project

```
cpps-native/
├── cpps.py              # Entry point (CLI + REPL)
├── src/
│   ├── tokens.py        # Token types
│   ├── lexer.py         # Tokenizer
│   ├── parser.py        # Parser & AST
│   └── interpreter.py   # Interpreter
└── README.md
```

---

🔧 Built-in Functions

I/O

· io::println(msg) - In với newline
· io::print(msg) - In không newline
· io::input() - Đọc input

Toán học

· math::sqrt(x), math::sin(x), math::cos(x)
· PI, E, TAU, INF, NAN

Collections

· len(collection) - Độ dài
· map(fn, list) - Áp dụng hàm
· filter(fn, list) - Lọc
· reduce(fn, list) - Gộp
· sorted(list) - Sắp xếp
· unique(list) - Loại bỏ trùng

File I/O

· file::read(path) - Đọc file
· file::write(path, content) - Ghi file
· file::exists(path) - Kiểm tra tồn tại

JSON

· json::parse(string) - Parse JSON
· json::stringify(obj) - Chuyển thành JSON

Time

· time::now() - Thời gian hiện tại
· time::sleep(seconds) - Tạm dừng

System

· sys::exit(code) - Thoát chương trình
· sys::args() - Arguments dòng lệnh

---

📝 Ví Dụ Hoàn Chỉnh

Calculator

```cpps
module calculator

++ calc <~ (a: float, b: float, op: string) -> float ** {
    ?~ op {
        "+" => { <- a + b },
        "-" => { <- a - b },
        "*" => { <- a * b },
        "/" => { 
            ?? b == 0 ** {
                !! "Cannot divide by zero"
            } -- else ** {
                <- a / b
            }
        },
        _ => { !! "Invalid operator" }
    }
}

++ main <~ () -> int ** {
    result := calc(10, 5, "+")
    ~> io::println("10 + 5 = {}", result)
    <- 0
}
```

Guess Game

```cpps
module guess_game

++ main <~ () -> int ** {
    secret := 42
    attempts :: mut int = 0
    
    ~> io::println("Welcome to Guess the Number!")
    ~> io::println("Guess a number from 1-100")
    
    while true ** {
        guess_str := io::input("Your guess: ")
        guess := to_int(guess_str)
        
        ?? guess == secret ** {
            attempts += 1
            ~> io::println("Correct in {} attempts!", attempts)
            break
        } -- elif guess < secret ** {
            ~> io::println("Too low")
            attempts += 1
        } -- else ** {
            ~> io::println("Too high")
            attempts += 1
        }
    }
    
    <- 0
}
```

---

🧩 Tính Năng Nâng Cao

1. Pattern Matching

```cpps
?~ value {
    (x, y) if x > y => { ... },
    (0, _) => { ... },
    _ => { ... }
}
```

2. Reflection

```cpps
@reflect obj
```

3. Macros

```cpps
@macro_tok my_macro(arg1, arg2)
@macro_ast code_generator(expr)
```

4. Generics

```cpps
++ max<T> <~ (a: T, b: T) -> T ** {
    ?? a > b ** { <- a } -- else ** { <- b }
}
```

5. Trait và Impl

```cpps
trait Printable -> {
    ++ print <~ () -> void ** { ... }
}

impl Printable for Dog -> {
    ++ print <~ () -> void ** {
        ~> io::println("Dog: {}", @.name)
    }
}
```

---

🤝 Đóng Góp

1. Fork repository
2. Tạo branch mới (git checkout -b feature/amazing-feature)
3. Commit thay đổi (git commit -m 'Add amazing feature')
4. Push lên branch (git push origin feature/amazing-feature)
5. Mở Pull Request

---

📄 License

MIT License

---

🌟 Tác Giả

· Mark-Vem - GitHub

---

📞 Liên Hệ

· GitHub: Mark-Vem/CPPS

---

CPPS v2.0.0

"Tương lai của lập trình là sự đơn giản trong phức tạp"
