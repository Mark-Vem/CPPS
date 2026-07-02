---

🚀 CPPS - CP+* (C-Plus-Plus-Star) Language

CPPS là trình thông dịch cho ngôn ngữ CP+* (C-Plus-Plus-Star) - một ngôn ngữ lập trình hiện đại với cú pháp độc đáo.

---

⚡ Bắt Đầu Nhanh

Cài Đặt

```bash
# Clone dự án
git clone https://github.com/Mark-Vem/CPPS.git
cd CPPS

# Chạy chương trình CP+* (yêu cầu Python 3.8+)
python cpps.py hello.cpps
```

Các Lệnh Cơ Bản

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

📖 Cú Pháp Cơ Bản

```cpps
-- Biến
x := 42                    -- Bất biến
name :: mut string = ""    -- Có thể thay đổi

-- Hàm
++ add <~ (a: int, b: int) -> int ** {
    <- a + b
}

-- Điều kiện
?? x > 0 ** {
    ~> io::println("Positive")
} -- else ** {
    ~> io::println("Not positive")
}

-- Vòng lặp
<> i :: [1, 2, 3] ** {
    ~> io::println("{}", i)
}

-- Pattern matching
?~ score {
    90..=100 => { ~> io::println("Excellent!") },
    70..89   => { ~> io::println("Good") },
    _        => { ~> io::println("Keep trying") }
}

-- Class
class Dog -> {
    name :: mut string = ""
    ++ new <~ (n: string) ** { @.name = n }
    ++ speak <~ () ** { ~> io::println("{} says Woof!", @.name) }
}

dog := Dog::new("Rex")
dog:speak()
```

---

🛠️ REPL Commands

Trong REPL (python cpps.py), bạn có thể sử dụng:

Lệnh Chức năng
:help Hiển thị trợ giúp
:quit Thoát
:clear Xóa màn hình
:env Hiển thị biến
:ast <code> Hiển thị AST
:tokens <code> Hiển thị tokens
:time <code> Đo thời gian

---

📁 Cấu Trúc Dự Án

```
CPPS/
├── cpps.py              # Entry point
├── src/
│   ├── tokens.py        # Định nghĩa token
│   ├── lexer.py         # Tokenizer
│   ├── parser.py        # Parser
│   └── interpreter.py   # Interpreter
└── README.md
```

---

🧩 Tính Năng Chính

· Ownership: own<T>, share<T>, borrow<T>
· OOP: Class, struct, trait, impl, inheritance
· Concurrency: Goroutines (go), Channels
· Pattern Matching: ?~
· Generics: Type parameters
· Error Handling: Try/catch, Result<Ok, Err>
· Reflection: @reflect
· Macros: @macro_tok, @macro_ast

---

🔧 Built-in Functions

```cpps
-- I/O
~> io::println("Hello")
io::input("Prompt: ")

-- Toán học
math::sqrt(16)    -- 4.0
math::sin(0)      -- 0.0
PI, E, INF, NAN

-- Collections
len([1, 2, 3])    -- 3
map(double, [1,2,3])

-- File
file::read("data.txt")
file::write("out.txt", "content")

-- JSON
json::parse('{"x": 1}')
json::stringify(obj)

-- Time
time::now()
time::sleep(1)
```

---

📝 Ví Dụ Hoàn Chỉnh

Calculator

```cpps
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
```

Guess Game

```cpps
++ main <~ () -> int ** {
    secret := 42
    
    while true ** {
        guess := to_int(io::input("Guess: "))
        
        ?? guess == secret ** {
            ~> io::println("Correct!")
            break
        } -- elif guess < secret ** {
            ~> io::println("Too low")
        } -- else ** {
            ~> io::println("Too high")
        }
    }
    <- 0
}
```

---

📄 License

MIT License

🌟 Tác Giả

· Mark-Vem

---

CPPS v2.0.0
