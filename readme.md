# My Clang Format

🧹 A simple `.clang-format` file that enforces a clean, Stroustrup-like C++ code style.

---

## 💡 Highlights

- Opening braces `{` on the **same line** (functions, classes, control statements, etc.)
- Indentation with **tabs**, not spaces
- `else`, `catch` on the **same line** as `}`
- Clean formatting for `switch`/`case`, enums, and class members
- No extra spacing in parentheses
- Aligned assignments and trailing comments

---

## 📐 Preview

```cpp
class Log {
public:
	enum Level { LevelError = 0, LevelWarning, LevelInfo };

private:
	Log() = delete;

public:
	static void Message(Level level, const char* message) {
		switch (level) {
			case LevelError: std::cout << "[ERROR]: " << message << std::endl; break;
			case LevelWarning: std::cout << "[WARNING]: " << message << std::endl; break;
			case LevelInfo: std::cout << "[INFO]: " << message << std::endl; break;
		}

		if (LevelError) {

		} else {

		}
	}
};
