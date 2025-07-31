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
#include <iostream>
#include <vector>

enum LogLevel {
	LevelError = 0,
	LevelWarning,
	LevelInfo
};

struct Vector2 {
	float x;
	float y;
};

class Logger {
public:
	static void Message(LogLevel level, const char* message) {
		switch (level) {
			case LevelError:   std::cout << "[ERROR]: "   << message << std::endl; break;
			case LevelWarning: std::cout << "[WARNING]: " << message << std::endl; break;
			case LevelInfo:    std::cout << "[INFO]: "    << message << std::endl; break;
		}

		if (level == LevelError) {
			std::cout << "Handling error..." << std::endl;
		} else if (level == LevelWarning) {
			std::cout << "Handling warning..." << std::endl;
		} else {
			std::cout << "Handling info..." << std::endl;
		}
	}

	static void LoopExample(const std::vector<int>& data) {
		for (int i = 0; i < data.size(); ++i) {
			if (data[i] % 2 == 0) {
				std::cout << "Even: " << data[i] << std::endl;
			} else {
				std::cout << "Odd: " << data[i] << std::endl;
			}
		}

		int i = 0;
		while (i < data.size()) {
			std::cout << "Element: " << data[i] << std::endl;
			++i;
		}
	}
};

int main() {
	Logger::Message(LevelWarning, "Something might be wrong.");
	std::vector<int> numbers = { 1, 2, 3, 4, 5 };
	Logger::LoopExample(numbers);
	return 0;
}

