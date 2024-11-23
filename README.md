# High-Frequency Trading System Simulation

This project simulates a **high-frequency trading system**, implementing key components such as market data feeds, order books, trading strategies, a backtesting engine, and monitoring alerts. The system provides a modular framework for testing and developing sophisticated trading algorithms. 

Designed with scalability and extensibility in mind, this project is ideal for showcasing algorithmic trading skills, software design expertise, and performance optimization techniques.

---

## Table of Contents

- [High-Frequency Trading System Simulation](#high-frequency-trading-system-simulation)
  - [Table of Contents](#table-of-contents)
  - [Installation](#installation)
    - [Steps to Build](#steps-to-build)
  - [Usage](#usage)
    - [Running the Simulation](#running-the-simulation)
      - [On Linux/MacOS](#on-linuxmacos)
      - [On Windows](#on-windows)
    - [Example Output](#example-output)
  - [Key Components](#key-components)
    - [1. **Market Data Feed**](#1-market-data-feed)
    - [2. **Order Book**](#2-order-book)
    - [3. **Trading Strategies**](#3-trading-strategies)
    - [4. **Backtesting Engine**](#4-backtesting-engine)
    - [5. **Monitoring \& Alerts**](#5-monitoring--alerts)
  - [Example Workflow](#example-workflow)
    - [Code Demonstration](#code-demonstration)
      - [Initializing a Market-Making Strategy](#initializing-a-market-making-strategy)
    - [Expected Output](#expected-output)
  - [License](#license)
  - [Technologies Used](#technologies-used)

---

## Installation

To build and run this project, ensure the following dependencies are installed:

- **C++ Compiler**: Compatible with `g++`, `clang++`, or `MSVC`
- **CMake**: Version `3.10` or higher
- **Boost Libraries**: For advanced mathematical computations
- **QuantLib (Optional)**: For financial calculations such as option Greeks

### Steps to Build

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/yourusername/high-frequency-trading-system-simulation.git
   cd high-frequency-trading-system-simulation
   ```

2. **Create a Build Directory**:
   ```bash
   mkdir build
   cd build
   ```

3. **Configure the Project Using CMake**:
   ```bash
   cmake ..
   ```

4. **Build the Project**:
   ```bash
   cmake --build .
   ```

---

## Usage

After building, run the simulation by executing the binary. Customize the simulation parameters by editing `main.cpp` to select different strategies, data inputs, and configurations.

### Running the Simulation

#### On Linux/MacOS
```bash
./high-frequency-trading-system-simulation
```

#### On Windows
```bash
.\Debug\high-frequency-trading-system-simulation.exe
```

---

### Example Output

Below is an example of output generated by the **Market-Making Strategy** during a simulation:

```
Analyzing market data for: AAPL
Generated order - ID: BID_ORDER_AAPL, Symbol: AAPL, Price: 148.5, Volume: 100, Type: BUY
Generated order - ID: ASK_ORDER_AAPL, Symbol: AAPL, Price: 151.5, Volume: 100, Type: SELL

Analyzing market data for: TSLA
Generated order - ID: BID_ORDER_TSLA, Symbol: TSLA, Price: 595.0, Volume: 100, Type: BUY
Generated order - ID: ASK_ORDER_TSLA, Symbol: TSLA, Price: 605.0, Volume: 100, Type: SELL
```

---

## Key Components

### 1. **Market Data Feed**
Simulates real-time market data or streams historical data for testing. Designed to support high-frequency updates and burst data patterns.

### 2. **Order Book**
Manages active buy/sell orders, matches trades based on market conditions, and supports partial or full order executions.

### 3. **Trading Strategies**
- **Trend-Following Strategy**: Places trades based on observed price trends.
- **Market-Making Strategy**: Provides liquidity by placing bid and ask orders around the current market price.

### 4. **Backtesting Engine**
Simulates trading strategies using historical market data. Evaluates performance based on predefined metrics such as profitability, Sharpe ratio, and drawdown.

### 5. **Monitoring & Alerts**
Tracks critical events, logs activity, and generates alerts with customizable severity levels (e.g., `LOW`, `MEDIUM`, `HIGH`).

---

## Example Workflow

### Code Demonstration

#### Initializing a Market-Making Strategy
```cpp
#include "trading_strategy/MarketMakingStrategy.hpp"
#include "order_book/Order.hpp"

int main() {
    // Create a MarketMakingStrategy instance
    MarketMakingStrategy marketMaker;

    // Simulated market data
    std::vector<Quote> quotes = {
        Quote("AAPL", 150.0, 1000),
        Quote("TSLA", 600.0, 800),
    };

    // Generate orders based on market data
    std::vector<Order> orders = marketMaker.generateOrders(quotes);

    return 0;
}
```

---

### Expected Output

```plaintext
Analyzing market data for: AAPL
Generated order - ID: BID_ORDER_AAPL, Symbol: AAPL, Price: 148.5, Volume: 100, Type: BUY
Generated order - ID: ASK_ORDER_AAPL, Symbol: AAPL, Price: 151.5, Volume: 100, Type: SELL

Analyzing market data for: TSLA
Generated order - ID: BID_ORDER_TSLA, Symbol: TSLA, Price: 594.0, Volume: 100, Type: BUY
Generated order - ID: ASK_ORDER_TSLA, Symbol: TSLA, Price: 606.0, Volume: 100, Type: SELL
```

---

## License

This project is licensed under the **MIT License**. Refer to the [LICENSE](LICENSE) file for more details.

---

## Technologies Used

This project was developed using the following tools and technologies:

- **Visual Studio Community Edition**: Integrated development environment (IDE) for C++ development.
- **vcpkg**: Package manager for managing C++ libraries such as Boost and QuantLib.
- **C++20**: Programming language used for developing the project, utilizing modern C++ features like concepts, coroutines, and more.
