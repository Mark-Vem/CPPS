---

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=32&pause=1000&color=00D4FF&center=true&vCenter=true&width=600&lines=CP+*+(C-Plus-Plus-Star);Ng%C3%B4n+Ng%E1%BB%AF+L%E1%BA%ADp+Tr%C3%ACnh+Hi%E1%BB%87n+%C4%90%E1%BA%A1i" alt="Typing SVG" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/version-2.0.0-00D4FF?style=for-the-badge&logo=git&logoColor=white" />
  <img src="https://img.shields.io/badge/python-3.8%2B-3776AB?style=for-the-badge&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/license-MIT-FF6B6B?style=for-the-badge" />
  <img src="https://img.shields.io/badge/status-stable-00C853?style=for-the-badge" />
  <img src="https://img.shields.io/badge/PRs-welcome-brightgreen?style=for-the-badge" />
</p>

<p align="center">
  <b>⚡ Mạnh mẽ như C++ · 🦀 An toàn như Rust · 🐍 Thanh lịch như Python</b>
</p>

---

📖 Giới Thiệu

CP+* (C-Plus-Plus-Star) là ngôn ngữ lập trình đa năng, được thiết kế để kết hợp những điểm mạnh nhất của các ngôn ngữ hàng đầu. Với cú pháp độc đáo và hiện đại, CP+* mang đến trải nghiệm lập trình thú vị và hiệu quả.

✨ Tính Năng Nổi Bật

Tính Năng Mô Tả
⚡ Hiệu Năng Cao Ownership system, zero-cost abstractions, quản lý bộ nhớ thông minh
🦺 An Toàn Tuyệt Đối Ownership, borrowing, lifetime checking - không còn lo lỗi bộ nhớ
🎯 Hiện Đại & Linh Hoạt Pattern matching, concurrency, OOP, generics, macros, reflection
📦 Dễ Dàng Mở Rộng Module system, import/export, namespace, package management

---
---

💻 Ví Dụ Cơ Bản

1. Hello World

```cpps
++ main <~ () -> int ** {
    name := "World"
    ~> io::println("Hello, {}!", name)
    <- 0
}
```

2. Biến và Kiểu Dữ Liệu

```cpps
-- Biến bất biến
x := 42
message := "CP+* thật tuyệt vời!"

-- Biến mutable
counter :: mut int = 0
score :: mut float = 95.5

-- Ownership
own<string> owned_name := "Sở hữu độc quyền"
share<int> shared_value := 100
borrow<float> borrowed := 3.14
```

3. Hàm và Tham Số

```cpps
-- Hàm cơ bản
++ add <~ (a: int, b: int) -> int ** {
    <- a + b
}

-- Hàm với generic
++ max<T> <~ (a: T, b: T) -> T ** {
    ?? a > b ** { <- a } -- else ** { <- b }
}
```

4. Điều Kiện và Rẽ Nhánh

```cpps
?? score >= 90 ** {
    ~> io::println("Xuất sắc!")
} -- elif score >= 70 ** {
    ~> io::println("Tốt")
} -- else ** {
    ~> io::println("Cần cố gắng")
}
```

5. Vòng Lặp

```cpps
-- For-each
<> item :: items ** {
    ~> io::println("Item: {}", item)
}

-- While
count :: mut int = 0
while count < 5 ** {
    ~> io::println("Count: {}", count)
    count += 1
}
```

6. Pattern Matching

```cpps
?~ value {
    1 => { ~> io::println("Một") },
    2 => { ~> io::println("Hai") },
    3 => { ~> io::println("Ba") },
    _ => { ~> io::println("Khác") }
}

?~ point {
    (0, 0) => { ~> io::println("Gốc tọa độ") },
    (x, y) => { ~> io::println("Điểm: ({}, {})", x, y) }
}
```

---

🏗️ Lập Trình Hướng Đối Tượng

1. Class Cơ Bản

```cpps
class Animal -> {
    name :: mut string = ""
    age :: mut int = 0
    
    ++ new <~ (n: string, a: int) ** {
        @.name = n
        @.age = a
    }
    
    ++ speak <~ () -> void ** {
        ~> io::println("{} says: ...", @.name)
    }
}
```

2. Kế Thừa

```cpps
class Dog : Animal -> {
    breed :: string = "Unknown"
    
    ++ new <~ (n: string, a: int, b: string) ** {
        @.name = n
        @.age = a
        @.breed = b
    }
    
    @@override
    ++ speak <~ () -> void ** {
        ~> io::println("{} says: Woof!", @.name)
    }
}
```

3. Trait và Impl

```cpps
trait Printable -> {
    ++ print <~ () -> void ** {
        ~> io::println("Printing...")
    }
}

impl Printable for Dog -> {
    ++ print <~ () -> void ** {
        ~> io::println("Dog: {}, {}, {}", @.name, @.age, @.breed)
    }
}
```

---

🔄 Concurrency và Goroutines

1. Goroutine

```cpps
go print_message("Hello from goroutine!")

++ print_message <~ (msg: string) -> void ** {
    ~> io::println("{}", msg)
}
```

2. Channels

```cpps
ch := Channel::new(10)

go producer(ch)
go consumer(ch)

++ producer <~ (ch: Channel) -> void ** {
    <> i :: 0..5 ** {
        ch:send(i)
        time::sleep(0.5)
    }
    ch:close()
}

++ consumer <~ (ch: Channel) -> void ** {
    while true ** {
        data := ch:recv()
        ?? data == none ** { break }
        ~> io::println("Received: {}", data)
    }
}
```

---

🛡️ Xử Lý Lỗi

1. Try/Catch

```cpps
try ** {
    result := risky_operation()
    ~> io::println("Success: {}", result)
} catch (e) ** {
    ~> io::println("Error: {}", e)
} finally ** {
    ~> io::println("Cleanup")
}
```

2. Result Type

```cpps
++ divide <~ (a: float, b: float) -> Result<float, string> ** {
    ?? b == 0 ** { <- Err("Cannot divide by zero") }
    -- else ** { <- Ok(a / b) }
}

result := divide(10, 0)
?~ result {
    Ok(value) => { ~> io::println("Result: {}", value) },
    Err(err) => { ~> io::println("Error: {}", err) }
}
```

---

🛠️ Cài Đặt

```bash
git clone https://github.com/Mark-Vem/CPPS.git
cd CPPS/cpps-native
python cpps.py hello.cpps
```

Yêu Cầu: Python 3.8+

---

📋 CLI Commands

```bash
python cpps.py file.cpps              # Chạy file
python cpps.py file.cpps --verbose    # Chạy với debug
python cpps.py --repl                 # Khởi động REPL
python cpps.py -e 'x := 42'           # Chạy code inline
python cpps.py --ast file.cpps        # Hiển thị AST
python cpps.py --tokens file.cpps     # Hiển thị tokens
python cpps.py --version              # Hiển thị version
python cpps.py --help                 # Hiển thị trợ giúp
```

---

🖥️ REPL Commands

Lệnh Chức năng
:help / :h Hiển thị trợ giúp
:quit / :q Thoát REPL
:clear / :c Xóa màn hình
:reset Reset interpreter
:env Hiển thị biến
:ast <code> Hiển thị AST
:tokens <code> Hiển thị tokens
:time <code> Đo thời gian
:type <expr> Hiển thị kiểu
:load <file> Load file .cpps

---

📂 Cấu Trúc Dự Án

```
CPPS/
├── cpps.py              # Entry point
├── src/
│   ├── tokens.py        # Định nghĩa token
│   ├── lexer.py         # Tokenizer
│   ├── parser.py        # Parser & AST
│   └── interpreter.py   # Interpreter
└── README.md
```

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
            ?? b == 0 ** { !! "Cannot divide by zero" }
            -- else ** { <- a / b }
        },
        _ => { !! "Invalid operator" }
    }
}

++ main <~ () -> int ** {
    ~> io::println("10 + 5 = {}", calc(10, 5, "+"))
    <- 0
}
```

Guess Game

```cpps
module guess_game

++ main <~ () -> int ** {
    secret := 42
    attempts :: mut int = 0
    
    ~> io::println("Chào mừng đến với trò chơi Đoán Số!")
    
    while true ** {
        guess := to_int(io::input("Số của bạn: "))
        attempts += 1
        
        ?? guess == secret ** {
            ~> io::println("Chính xác! {} lần", attempts)
            break
        } -- elif guess < secret ** {
            ~> io::println("Quá thấp")
        } -- else ** {
            ~> io::println("Quá cao")
        }
    }
    <- 0
}
```

---

🧩 Tính Năng Nâng Cao

Ownership

```cpps
own<string> s := "Hello"
share<string> ref := s
borrow<string> temp := s
```

Generics

```cpps
++ max<T> <~ (a: T, b: T) -> T ** {
    ?? a > b ** { <- a } -- else ** { <- b }
}
```

Reflection

```cpps
@reflect obj
```

Macros

```cpps
@macro_tok my_macro(arg1, arg2)
@macro_ast code_generator(expr)
```

---

🤝 Đóng Góp

1. Fork repository
2. Tạo branch mới: git checkout -b feature/amazing
3. Commit thay đổi: git commit -m 'Add amazing feature'
4. Push lên branch: git push origin feature/amazing
5. Mở Pull Request

---

📄 License

MIT License

---

🌟 Tác Giả

· Mark-Vem - GitHub

---

<p align="center">
  <b>💫 CPPS v2.0.0 · Advanced Edition</b><br/>
  <i>"Tương lai của lập trình là sự đơn giản trong phức tạp"</i>
</p>

<p align="center">
  <a href="https://github.com/Mark-Vem/CPPS">
    <img src="https://img.shields.io/badge/⭐_Star_on_GitHub-181717?style=for-the-badge&logo=github&logoColor=white" />
  </a>
</p>

---

<p align="center">
  Made with ❤️ by CPPS Team
</p>
