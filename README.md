# Feature Extraction for 3D Models

This repository contains a Python script for extracting features from 3D models, specifically STL files. The script is designed to process 3D models of blood vessels, focusing on the analysis of aneurysms and thrombus volumes. It provides functionalities for slicing, centerline approximation, diameter calculation, and volume estimation.

## Features

- **Splitting STL Files**: Divides an STL file containing multiple solids into separate files.
- **Slicing Along Z-Axis**: Generates slices along the z-axis for visualization and analysis.
- **Centerline Approximation**: Approximates the centerline of the 3D model using splines.
- **Diameter Calculation**: Calculates the diameter of slices and the minimum distance to the center.
- **Volume Estimation**: Estimates the volume of aneurysms and thrombus.
- **Graphical User Interface (GUI)**: Provides a simple GUI for selecting input directories and managing history.

## Requirements

- Python 3.x
- PyVista
- NumPy
- VTK
- PyMeshFix
- PySimpleGUI

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/feature-extraction-3d.git
   cd feature-extraction-3d
   ```

2. Install the required Python packages:
   ```bash
   pip install -r requirements.txt
   ```

## Usage

1. **Run the Script**:
   ```bash
   python FeatureExtraction.py
   ```

2. **Select Input Directory**:
   - The GUI will prompt you to select a directory containing STL files.
   - You can browse for a directory, use the last used directory, or clear the history.

3. **Process Files**:
   - The script will process each STL file in the selected directory.
   - It will generate slices, approximate the centerline, calculate diameters, and estimate volumes.

4. **View Results**:
   - The script will generate visualizations of the slices, centerline, and volumes.
   - Results are saved in a JSON file (`datos.json`).

## Functions

- **`split_model(input_file)`**: Splits an STL file into separate files based on solids.
- **`slice_z(mesh, n_slices=100)`**: Generates slices along the z-axis of a mesh.
- **`distance2points_3d(point1, point2)`**: Calculates the Euclidean distance between two 3D points.
- **`diam_calc(slice, center)`**: Calculates the diameter of a slice and the minimum distance to the center.
- **`find_blocks(list)`**: Groups consecutive positions within a certain distance.
- **`load_stl(filename)`**: Loads an STL file and extracts vertices and faces.
- **`save_stl(filename, faces)`**: Saves vertex and face information to an STL file.
- **`add2vectors(v1, v2)`**: Adds two vectors and returns the result as a unit vector.
- **`centerline_aprox(slices, n=100)`**: Approximates the centerline using splines.
- **`ortogonal_slices(centerline, mesh, n=100)`**: Generates orthogonal slices based on the centerline.

## Output

- **Visualizations**: Interactive 3D visualizations of the mesh, slices, and centerline.
- **JSON File**: Contains geometrical parameters such as aneurysm length, maximum diameter, sac index, centerline length, tortuosity, aneurysm volume, thrombus volume, and total volume.

## Example

```python
# Example usage of the script
python FeatureExtraction.py
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- **PyVista**: For 3D visualization and mesh processing.
- **PyMeshFix**: For mesh repair and volume estimation.
- **PySimpleGUI**: For the graphical user interface.

## Contact

For any questions or suggestions, please contact [your email].

---

This README provides an overview of the script, its functionalities, and how to use it. For more detailed information, refer to the code comments and documentation.