---

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=28&pause=1000&color=00D4FF&center=true&vCenter=true&width=500&lines=CP+*+(C-Plus-Plus-Star);Ng%C3%B4n+Ng%E1%BB%AF+L%E1%BA%ADp+Tr%C3%ACnh+Hi%E1%BB%87n+%C4%90%E1%BA%A1i" alt="Typing SVG" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/version-2.0.0-00D4FF?style=for-the-badge&logo=git&logoColor=white" alt="Version"/>
  <img src="https://img.shields.io/badge/python-3.8+-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python"/>
  <img src="https://img.shields.io/badge/license-MIT-FF6B6B?style=for-the-badge" alt="License"/>
  <img src="https://img.shields.io/badge/status-stable-00C853?style=for-the-badge" alt="Status"/>
</p>

<p align="center">
  <b>Manh me nhu C++ · An toan nhu Rust · Thanh lich nhu Python</b>
</p>

<hr/>

📖 Gioi Thieu

CP+ (C-Plus-Plus-Star) la ngon ngu lap trinh da nang, ket hop tinh hoa cua nhung ngon ngu hang dau:

<table>
<tr>
<td width="33%" align="center">
  <h3>⚡ Hieu Nang Cao</h3>
  <p>Ownership system, zero-cost abstractions, efficient memory management</p>
</td>
<td width="33%" align="center">
  <h3>🦺 An Toan</h3>
  <p>Ownership, borrowing, lifetime checking - khong lo loi bo nho</p>
</td>
<td width="33%" align="center">
  <h3>🎯 Hien Dai</h3>
  <p>Pattern matching, concurrency, OOP, generics, macros, reflection</p>
</td>
</tr>
</table>

---

🎯 Cu Phap Dac Biet

<table>
<tr>
<th>Ky hieu</th>
<th>Y nghia</th>
<th>Vi du</th>
</tr>
<tr>
<td><code>:=</code></td>
<td>Bien bat bien</td>
<td><code>x := 42</code></td>
</tr>
<tr>
<td><code>:: mut</code></td>
<td>Bien mutable</td>
<td><code>y :: mut int = 0</code></td>
</tr>
<tr>
<td><code>++</code></td>
<td>Dinh nghia ham</td>
<td><code>++ add &lt;~ (a, b) ** { ... }</code></td>
</tr>
<tr>
<td><code>&lt;~</code></td>
<td>Mui ten tham so</td>
<td><code>++ fn &lt;~ (p: int) ** { ... }</code></td>
</tr>
<tr>
<td><code>-></code></td>
<td>Kieu tra ve</td>
<td><code>-&gt; int</code></td>
</tr>
<tr>
<td><code>**</code></td>
<td>Mo dau block</td>
<td><code>** { body }</code></td>
</tr>
<tr>
<td><code>??</code></td>
<td>Dieu kien If</td>
<td><code>?? x &gt; 0 ** { ... }</code></td>
</tr>
<tr>
<td><code>&lt;&gt;</code></td>
<td>Vong lap For</td>
<td><code>&lt;&gt; i :: list ** { ... }</code></td>
</tr>
<tr>
<td><code>~&gt;</code></td>
<td>In ra</td>
<td><code>~&gt; io::println("Hello!")</code></td>
</tr>
<tr>
<td><code>&lt;-</code></td>
<td>Return</td>
<td><code>&lt;- value</code></td>
</tr>
<tr>
<td><code>!!</code></td>
<td>Panic</td>
<td><code>!! "error"</code></td>
</tr>
<tr>
<td><code>!&gt;</code></td>
<td>Break</td>
<td><code>!&gt;</code></td>
</tr>
<tr>
<td><code>!&gt;&gt;</code></td>
<td>Continue</td>
<td><code>!&gt;&gt;</code></td>
</tr>
<tr>
<td><code>?~</code></td>
<td>Pattern match</td>
<td><code>?~ value { ... }</code></td>
</tr>
<tr>
<td><code>@</code></td>
<td>Self reference</td>
<td><code>@.field</code></td>
</tr>
<tr>
<td><code>::</code></td>
<td>Method call</td>
<td><code>obj:method()</code></td>
</tr>
<tr>
<td><code>@@</code></td>
<td>Annotation</td>
<td><code>@@override</code></td>
</tr>
<tr>
<td><code>own&lt;T&gt;</code></td>
<td>Ownership</td>
<td><code>own&lt;int&gt; x := 42</code></td>
</tr>
<tr>
<td><code>share&lt;T&gt;</code></td>
<td>Shared ref</td>
<td><code>share&lt;string&gt; name</code></td>
</tr>
<tr>
<td><code>borrow&lt;T&gt;</code></td>
<td>Borrow</td>
<td><code>borrow&lt;int&gt; ptr</code></td>
</tr>
</table>

---

💻 Vi Du

Hello World

```cpps
++ main <~ () -> int ** {
    name := "World"
    ~> io::println("Hello, {}!", name)
    <- 0
}
```

Class va OOP

```cpps
class Dog -> {
    name :: mut string = ""
    
    ++ new <~ (n: string) ** {
        @.name = n
    }
    
    ++ speak <~ () ** {
        ~> io::println("{} says: Woof!", @.name)
    }
}

dog := Dog::new("Rex")
dog:speak()  -- Rex says: Woof!
```

Pattern Matching

```cpps
?~ score {
    90..=100 => { ~> io::println("Xuat sac!") },
    70..89   => { ~> io::println("Tot") },
    _        => { ~> io::println("Can co gang") }
}
```

Concurrency

```cpps
ch := Channel::new(10)

go process(ch)
ch:send(42)

++ process <~ (ch: Channel) ** {
    data := ch:recv()
    ~> io::println("Received: {}", data)
}
```

---

🛠️ Cai Dat

```bash
# Clone du an
git clone https://github.com/Mark-Vem/CPPS.git
cd CPPS/cpps-native

# Chay chuong trinh CP+*
python cpps.py hello.cpps
```

Yeu Cau

· Python 3.8 tro len

---

📋 CLI Commands

```bash
python cpps.py file.cpps              # Chay file
python cpps.py file.cpps --verbose    # Chay voi debug
python cpps.py --repl                 # Khoi dong REPL
python cpps.py -e 'x := 42'           # Chay code inline
python cpps.py --ast file.cpps        # Hien thi AST
python cpps.py --tokens file.cpps     # Hien thi tokens
python cpps.py --version              # Hien thi version
python cpps.py --help                 # Hien thi tro giup
```

---

🖥️ REPL Commands

<table>
<tr>
<th>Lenh</th>
<th>Chuc nang</th>
</tr>
<tr><td><code>:help</code> / <code>:h</code></td><td>Hien thi tro giup</td></tr>
<tr><td><code>:quit</code> / <code>:q</code></td><td>Thoat REPL</td></tr>
<tr><td><code>:clear</code> / <code>:c</code></td><td>Xoa man hinh</td></tr>
<tr><td><code>:reset</code></td><td>Reset interpreter</td></tr>
<tr><td><code>:env</code></td><td>Hien thi bien</td></tr>
<tr><td><code>:ast &lt;code&gt;</code></td><td>Hien thi AST</td></tr>
<tr><td><code>:tokens &lt;code&gt;</code></td><td>Hien thi tokens</td></tr>
<tr><td><code>:time &lt;code&gt;</code></td><td>Do thoi gian</td></tr>
<tr><td><code>:type &lt;expr&gt;</code></td><td>Hien thi kieu</td></tr>
<tr><td><code>:load &lt;file&gt;</code></td><td>Load file .cpps</td></tr>
</table>

---

📂 Cau Truc Du An

```
CPPS/
├── 📄 cpps.py              # Entry point
├── 📁 src/
│   ├── 📄 tokens.py        # Dinh nghia token
│   ├── 📄 lexer.py         # Tokenizer
│   ├── 📄 parser.py        # Parser & AST
│   └── 📄 interpreter.py   # Interpreter
└── 📄 README.md
```

---

🔧 Built-in Functions

I/O

```cpps
~> io::println("Hello")   -- In voi newline
~> io::print("Hello")     -- In khong newline
io::input("Prompt: ")     -- Doc input
```

Toan Hoc

```cpps
math::sqrt(16)    -- 4.0
math::sin(0)      -- 0.0
math::log(100)    -- 4.605
PI, E, TAU, INF, NAN
```

Collections

```cpps
len([1, 2, 3])          -- 3
map(double, [1,2,3])    -- [2,4,6]
filter(is_positive, []) -- []
reduce(add, [1,2,3])    -- 6
sorted([3,1,2])         -- [1,2,3]
unique([1,1,2])         -- [1,2]
```

File I/O

```cpps
file::read("data.txt")
file::write("out.txt", "content")
file::exists("file.txt")
```

JSON

```cpps
json::parse('{"x": 1}')
json::stringify(obj)
```

Time

```cpps
time::now()
time::sleep(1)
time::millis()
```

System

```cpps
sys::exit(0)
sys::args()
sys::platform()
```

---

📝 Vi Du Hoan Chinh

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
    ~> io::println("10 * 5 = {}", calc(10, 5, "*"))
    <- 0
}
```

Guess Game

```cpps
module guess_game

++ main <~ () -> int ** {
    secret := 42
    attempts :: mut int = 0
    
    ~> io::println("🎯 Welcome to Guess the Number!")
    ~> io::println("I'm thinking of a number (1-100)")
    
    while true ** {
        guess := to_int(io::input("Your guess: "))
        attempts += 1
        
        ?? guess == secret ** {
            ~> io::println("🎉 Correct! You got it in {} tries!", attempts)
            break
        } -- elif guess < secret ** {
            ~> io::println("⬆️ Too low")
        } -- else ** {
            ~> io::println("⬇️ Too high")
        }
    }
    <- 0
}
```

---

🧩 Tinh Nang Nang Cao

Ownership

```cpps
own<string> s := "Hello"        -- So huu doc quyen
share<string> ref := s          -- Tham chieu chia se
borrow<string> temp := s        -- Muon tam thoi
```

Pattern Matching

```cpps
?~ value {
    (x, y) if x > y => { ... },
    (0, _) => { ... },
    _ => { ... }
}
```

Generics

```cpps
++ max<T> <~ (a: T, b: T) -> T ** {
    ?? a > b ** { <- a } -- else ** { <- b }
}
```

Trait & Impl

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

🤝 Dong Gop

1. Fork repository
2. Tao branch moi: git checkout -b feature/amazing
3. Commit thay doi: git commit -m 'Add amazing feature'
4. Push len branch: git push origin feature/amazing
5. Mo Pull Request

---

📄 License

MIT License - Xem file LICENSE de biet them chi tiet.

---

🌟 Tac Gia

· Mark-Vem - GitHub

---

<p align="center">
  <b>💫 CPPS v2.0.0 · Advanced Edition</b><br/>
  <i>"Tuong lai cua lap trinh la su don gian trong phuc tap"</i>
</p>

<p align="center">
  <a href="https://github.com/Mark-Vem/CPPS">
    <img src="https://img.shields.io/badge/⭐_Star_on_GitHub-181717?style=for-the-badge&logo=github&logoColor=white"/>
  </a>
</p>

<hr/>

<p align="center">
  Made with ❤️ by CPPS Team
</p>
