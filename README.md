# Periodic Table Application

This project is an Android application that provides users with a detailed and interactive Periodic Table. The app is implemented in **Kotlin** and leverages **RecyclerView**, **ViewModel**, and **LiveData** for a smooth and efficient user experience.  

## 📂 Directory Structure  

All the source files are located in the `app/src/main/java/com/fujitalabs/periodic_table` directory. Below is an overview of the key files and their responsibilities:  

### **1. `Element.kt`**  
This file defines the `Element` data class, which represents the properties of an individual element in the periodic table.  

**Fields:**  
- `atomicNumber: Int` - The atomic number of the element.  
- `name: String` - The name of the element.  
- `symbol: String` - The chemical symbol of the element.  
- `group: Int` - The group number in the periodic table.  
- `period: Int` - The period number in the periodic table.  

---

### **2. `ElementRepository.kt`**  
This file manages the data source of the periodic table. It fetches the list of elements, either from a local JSON file or a database (if implemented in the future).  

**Responsibilities:**  
- Fetch and return a list of `Element` objects.  
- Abstracts data storage from the UI layer.  

---

### **3. `PeriodicTableViewModel.kt`**  
This is the ViewModel class that mediates between the UI and the data layer. It uses `LiveData` to observe data changes.  

**Responsibilities:**  
- Hold the `LiveData` object for the list of elements.  
- Fetch data from the `ElementRepository` and expose it to the UI.  

---

### **4. `ElementAdapter.kt`**  
The adapter for the RecyclerView that displays the periodic table elements in a grid layout.  

**Responsibilities:**  
- Binds each `Element` object to the corresponding view in the RecyclerView.  
- Optimizes performance by recycling views.  

**Key methods:**  
- `onBindViewHolder()` - Binds data to each grid cell.  
- `getItemCount()` - Returns the number of items.  

---

### **5. `MainActivity.kt`**  
The main entry point of the application, managing the lifecycle of the app.  

**Responsibilities:**  
- Initialize the RecyclerView and set the `ElementAdapter`.  
- Observe the `PeriodicTableViewModel` for data updates.  
- Display the periodic table in a grid format.  

---

## 🛠️ Features  

1. **Interactive Periodic Table**: View all elements in a grid format with their atomic number, symbol, and name.  
2. **Responsive UI**: Smooth scrolling and interaction using RecyclerView.  
3. **LiveData Integration**: Real-time updates to the UI when data changes.  
4. **Separation of Concerns**: Clean architecture with a well-defined data, ViewModel, and UI layer.  

---

## 🚀 Getting Started  

### Prerequisites  
- Android Studio (Arctic Fox or newer)  
- Kotlin 1.5 or later  

### Setup Instructions  

1. Clone the repository.  
   ```bash
   git clone <repository-url>
   cd periodic_table_app
   ```  

2. Open the project in Android Studio.  

3. Build the project and resolve any dependencies.  

4. Run the application on an emulator or a physical device.  

---

## 📜 Usage  

1. Launch the app to view the periodic table.  
2. Scroll through the table to explore various elements.  
3. Click on an element (optional future feature) to view its detailed properties.  

---

## 📂 File Format  

The element data can be stored in a local JSON file or fetched from an API (extendable). Ensure the data source includes the following fields for each element:  
```json
{
  "atomicNumber": 1,
  "name": "Hydrogen",
  "symbol": "H",
  "group": 1,
  "period": 1
}
```  

---

## 🤝 Contributing  

1. Fork the repository.  
2. Create a new branch for your feature/fix.  
   ```bash
   git checkout -b feature-name
   ```  
3. Commit your changes.  
   ```bash
   git commit -m "Add feature-name"
   ```  
4. Push to your branch.  
   ```bash
   git push origin feature-name
   ```  
5. Open a Pull Request.  

---

