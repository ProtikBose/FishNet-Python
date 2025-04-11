# FishNet-Python

# 📦 Google Street View Tile Grid Exporter

This tool processes Google Street View (GSV) image folders where each folder is named using **Web Mercator tile coordinates** (e.g., `24776_52606`). It generates a GeoJSON file that represents each folder as a square **grid polygon** on the map based on its tile position at a given zoom level (default: 17).

---

## 🗂 Folder Structure

Each subfolder in the root directory should follow the naming pattern:

```
<TILE_X>_<TILE_Y>
```

### Example:
```
24776_52606/
24777_52606/
24776_52607/
```

> Make sure: folder names **must** match this format for the script to work correctly.

---

## 📄 Output Format

The script generates a `tile_grids.geojson` file with one feature per folder. Each polygon represents the tile’s bounding box.

```json
{
  "type": "Feature",
  "properties": {
    "folder": "24776_52606"
  },
  "geometry": {
    "type": "Polygon",
    "coordinates": [
      [
        [-122.4646, 37.7841],
        [-122.4583, 37.7841],
        [-122.4583, 37.7780],
        [-122.4646, 37.7780],
        [-122.4646, 37.7841]
      ]
    ]
  }
}
```

---

## 🔧 How to Use

1. Set the path to your GSV folders in the script:

   ```python
   root_gsv_folder = "D:\\Path\\To\\GSV"
   ```

2. Define which folders you want to include (Optional):

   ```python
   selected_folder_list = ["24776_52606", "24777_52606"]
   ```

3. Run the script. It will create a `tile_grids.geojson` file in the working directory.

---


## 📜 License

This project is licensed under the [MIT License](LICENSE).  
Feel free to use, modify, and share!

---
