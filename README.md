## Car

### Structure 
```
car/
├── CMakeLists.txt
├── README.md
├── header/
│   ├── interfaces/
│   │   ├── ICar.hpp
│   │   ├── IEngine.hpp
│   │   ├── IFuelTank.hpp
│   │   └── IFuelTankDisplay.hpp
│   ├── car/
│   │   └── Car.hpp
│   ├── engine/
│   │   └── Engine.hpp
│   └── fuel/
│       ├── FuelTank.hpp
│       └── FuelTankDisplay.hpp
├── src/
│   ├── Car.cpp
│   ├── Engine.cpp
│   ├── FuelTank.cpp
│   └── FuelTankDisplay.cpp
└── unit_tests/
    ├── CMakeLists.txt
    ├── test_car.cpp
    ├── test_engine.cpp
    └── test_fuel_tank.cpp
```

