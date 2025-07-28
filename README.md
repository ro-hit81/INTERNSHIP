# Geoinformatics Research Internship

**Institution**: Geoinformatics Center, Asian Institute of Technology (AIT)  
**Research Focus**: Remote Sensing, GIS, and Environmental Monitoring using Google Earth Engine  
**Location**: Thailand  

## 🌟 Overview

This repository contains the research work and code developed during an internship at the Geoinformatics Center at the Asian Institute of Technology. The internship focused on advanced geospatial analysis, remote sensing applications, and environmental monitoring using Google Earth Engine (GEE) and various geospatial technologies.

## 🗂️ Project Structure

```
INTERNSHIP/
├── Data Scraping/              # Web scraping tools and utilities
├── Deep Learning/              # Deep learning applications for LULC mapping
├── Global Surface Water/       # Global surface water analysis scripts
└── Link to GEE stuff/         # Google Earth Engine code collection
    ├── CHIANG RAI/            # Chiang Rai province analysis
    │   ├── LULC               # Land Use Land Cover mapping
    │   └── SEASONAL IMAGE     # Seasonal image processing
    ├── UBON/                  # Ubon Ratchathani analysis
    │   ├── FLOOD              # Flood mapping and analysis
    │   ├── LULC UBON         # LULC classification for Ubon
    │   └── Season Image       # Seasonal imagery and NDWI analysis
    └── VIENTIANE/             # Vientiane, Laos analysis
        ├── DRY SEASON         # Dry season analysis
        └── WET SEASON         # Wet season analysis
```

## 🔬 Research Areas

### 1. **Land Use Land Cover (LULC) Mapping**
- **Objective**: Create comprehensive LULC maps for multiple Southeast Asian cities
- **Cities Studied**: Chiang Rai (Thailand), Ubon Ratchathani (Thailand), Vientiane (Laos)
- **Methodology**: Supervised classification using CART algorithm in Google Earth Engine
- **Data Source**: Sentinel-2 satellite imagery
- **Output**: Classified maps distinguishing water bodies, vegetation, urban areas, and other land cover types

### 2. **Seasonal Analysis**
- **Dry Season Mapping**: February-March timeframe analysis
- **Wet Season Mapping**: April-May and December analysis
- **Comparative Studies**: Seasonal variations in land cover and water distribution
- **Indices Used**: NDWI (Normalized Difference Water Index) for water body detection

### 3. **Flood Monitoring**
- **Focus Area**: Ubon Ratchathani flood analysis
- **Application**: Real-time flood extent mapping during monsoon periods
- **Methodology**: Binary classification (water/non-water) using machine learning
- **Temporal Analysis**: Multi-year flood pattern assessment

### 4. **Global Surface Water Analysis**
- **Data Source**: JRC Global Surface Water dataset (1984-2015)
- **Parameters Analyzed**:
  - Water occurrence frequency
  - Seasonal and permanent water classification
  - Water transition dynamics
  - Change detection over 35-year period

### 5. **Data Scraping and Automation**
- **Tool**: Beautiful Soup library for Python
- **Purpose**: Automated extraction of geospatial metadata and information from web sources
- **Application**: Enhancing datasets with additional contextual information

### 6. **Deep Learning Applications**
- **Focus**: Advanced LULC classification using deep learning techniques
- **Target Area**: Ubon city comprehensive mapping
- **Integration**: Combining traditional remote sensing with modern AI approaches

## 🛠️ Technical Implementation

### Google Earth Engine Scripts

#### **Chiang Rai Analysis**
- **Dry Season LULC**: [GEE Script](https://code.earthengine.google.com/851668b4a071a997cab807b56bc2c9ce)
- **Wet Season LULC**: [GEE Script](https://code.earthengine.google.com/5eb54b1606077811920a44d2a38c20b0)
- **Dry Season Imagery**: [GEE Script](https://code.earthengine.google.com/757011379ef0ead3f967f8cc49ac36f6)
- **Wet Season Imagery**: [GEE Script](https://code.earthengine.google.com/d74f1cd002cc7f5f2d0340b99b473144)

#### **Ubon Ratchathani Analysis**
- **Flood Mapping**: [GEE Script](https://code.earthengine.google.com/e1dfc6370fb36dcc306ad66eac0e03c4)
- **Dry Season LULC**: [GEE Script](https://code.earthengine.google.com/d20b77f515173d469502b319658eadb2)
- **Wet Season LULC**: [GEE Script](https://code.earthengine.google.com/42858a1954fe09d45708756788997976)
- **Dry Season Imagery**: [GEE Script](https://code.earthengine.google.com/fae9e72dde23e375a86f9349f079b864)
- **Wet Season Imagery**: [GEE Script](https://code.earthengine.google.com/29a6f41e89377364301a0d11e0a13524)

#### **Vientiane Analysis**
- **Dry Season**: [GEE Script](https://code.earthengine.google.com/16931f46fa2991d2d59ddedec8121702)
- **Wet Season**: [GEE Script](https://code.earthengine.google.com/f8b1d88570007459652405f439c125f0)

### Key Algorithms and Methods

#### **CART Classification**
```javascript
var classifier = ee.Classifier.cart().train({
  features: training,
  classProperty: 'landcover',
  inputProperties: bands
});
var classified = image.select(bands).classify(classifier);
```

#### **NDWI Calculation**
```javascript
var ndwi = image.normalizedDifference(['B3', 'B8']);
var ndwiViz = {min: 0.5, max: 1, palette: ['00FFFF', '0000FF']};
```

#### **Seasonal Image Filtering**
```javascript
var bound_image = image.filterBounds(boundary);
var s2_image = bound_image.filterDate('2019-02-02', '2019-02-05');
var mosaic_image = s2_image.mosaic();
```

## 📊 Research Outputs

### **Land Cover Classifications**
- **Classes Identified**: Water bodies, vegetation, urban areas, agricultural land
- **Accuracy Assessment**: Ground truth validation for classification accuracy
- **Temporal Comparison**: Multi-seasonal analysis for change detection

### **Water Body Analysis**
- **Permanent Water Mapping**: Year-round water presence identification
- **Seasonal Water Variation**: Monsoon impact on water distribution
- **Flood Risk Assessment**: Historical flood pattern analysis

### **Regional Studies**
1. **Chiang Rai Province**: Northern Thailand mountainous region analysis
2. **Ubon Ratchathani**: Northeastern Thailand Mekong River basin study
3. **Vientiane**: Cross-border Laos capital region investigation

## 🔧 Technologies Used

- **Google Earth Engine**: Primary cloud-based geospatial analysis platform
- **Sentinel-2 Imagery**: 10-30m resolution multispectral satellite data
- **JavaScript**: GEE code environment programming language
- **Python**: Data processing and web scraping (Beautiful Soup)
- **JRC Global Surface Water**: Long-term water dynamics dataset
- **CART Algorithm**: Classification and Regression Trees for supervised learning

## 📈 Key Findings

### **Seasonal Variations**
- Significant water body expansion during wet season (April-May)
- Urban area stability across seasons
- Agricultural land use changes following monsoon patterns

### **Regional Differences**
- **Chiang Rai**: Mountainous terrain with distinct seasonal water patterns
- **Ubon**: River-dominated landscape with extensive flood plains
- **Vientiane**: Urban-rural mix with Mekong River influence

### **Flood Patterns**
- Predictable annual flooding cycles in Ubon region
- Climate change impacts on traditional flooding patterns
- Infrastructure vulnerability assessment capabilities

## 🎓 Learning Outcomes

- **Advanced GEE Proficiency**: Comprehensive understanding of cloud-based geospatial analysis
- **Remote Sensing Expertise**: Multi-temporal satellite imagery analysis techniques
- **Machine Learning Applications**: Supervised classification for environmental monitoring
- **Regional Environmental Understanding**: Southeast Asian environmental patterns and challenges
- **Cross-border Analysis**: International collaboration and data sharing methodologies

## 🌍 Impact and Applications

### **Environmental Monitoring**
- Climate change impact assessment tools
- Water resource management support systems
- Agricultural planning and optimization

### **Disaster Management**
- Early flood warning system development
- Risk assessment and vulnerability mapping
- Emergency response planning support

### **Urban Planning**
- Land use change monitoring
- Sustainable development indicator tracking
- Infrastructure development guidance

## 📚 Related Publications and Presentations

*[Space for any publications, conference presentations, or reports generated from this internship work]*

## 🤝 Collaboration

### **Institutional Partners**
- **Asian Institute of Technology (AIT)** - Geoinformatics Center
- **Google Earth Engine Team** - Technical platform support
- **Regional Universities** - Cross-border research collaboration

### **Data Providers**
- European Space Agency (Sentinel-2 imagery)
- JRC Global Surface Water dataset
- Local government agencies for ground truth data

## 🔗 Useful Links

- [Asian Institute of Technology](https://www.ait.ac.th/)
- [Geoinformatics Center at AIT](https://www.geoinfo.ait.ac.th/)
- [Google Earth Engine](https://earthengine.google.com/)
- [JRC Global Surface Water Explorer](https://global-surface-water.appspot.com/)

## 📞 Contact

For questions about this research or collaboration opportunities:
- **Institution**: Geoinformatics Center, Asian Institute of Technology
- **Location**: Pathum Thani, Thailand
- **Research Domain**: Remote Sensing, GIS, Environmental Monitoring

---

**Note**: This internship work contributes to the broader understanding of Southeast Asian environmental dynamics and demonstrates the practical applications of cloud-based geospatial analysis for regional environmental monitoring and management.
