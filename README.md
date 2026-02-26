# Geocoding & Geolocation Automation (Google Apps Script)

This repository contains automation solutions focused on:

- Geocoding
- Geolocation
- Georeferencing
- Address normalization
- API integration

All implementations are built using **Google Apps Script** and designed to work directly with **Google Sheets**.

---

## Project Purpose

The goal of this repository is to demonstrate different approaches to address-to-coordinate conversion (geocoding) within spreadsheet-based workflows.

It showcases:

- API integration
- Proxy architecture
- Retry strategies
- Data normalization
- Automation inside Google Workspace
- Modular project organization

This project simulates real-world geospatial automation scenarios commonly used in:

- Public administration
- Logistics
- Urban planning
- Data analysis
- Operational monitoring

The project was created with the purpose of developing a database of geolocated addresses to support and supply data visualization and cartographic software tools.

---

# Repository Structure

- **geocoding-automation/**
  - **google-maps-geocoder/**
    - google-maps.gs
  - **nominatim-geocoder/**
    - nominatim.gs
    - worker-proxy.js
  - **GEOCODING_PROJECT_DOCUMENTATION.txt** 
  
---

# Implementations

## Google Maps Geocoding API

### Overview

This implementation uses the official Google Maps Geocoding API to convert addresses into:

- Latitude
- Longitude
- Postal code (when available)

### Flow

Google Sheets  
↓  
Google Apps Script  
↓  
Google Maps Geocoding API  

### Characteristics

- Requires API key
- High precision results
- Structured JSON response
- Subject to quota and billing limits
- Direct API integration (no proxy layer)

---

## OpenStreetMap Nominatim (With Proxy Worker)

### Overview

This implementation uses OpenStreetMap's Nominatim API through a proxy worker.

The proxy is required to:

- Provide proper API identification
- Add required headers
- Handle structured responses
- Avoid exposing direct API calls

### Flow

Google Sheets  
↓  
Google Apps Script (Client)  
↓  
Proxy Worker  
↓  
OpenStreetMap Nominatim API  

### Features

- Address normalization (removes diacritics)
- Multiple fallback address attempts
- Progressive retry strategy
- Filter-aware row processing
- Prevents overwriting existing coordinates
- Layered architecture (Client → Proxy → API)

---

# Technical Highlights

This repository demonstrates:

- Modular folder structure
- Separation of responsibilities
- External API communication
- Error handling
- Progressive retry logic
- Clean code organization
- Geospatial data automation

---

# Technologies Used

- Google Apps Script (JavaScript ES6)
- Google Sheets
- Google Maps Geocoding API
- OpenStreetMap Nominatim
- HTTP Requests (UrlFetchApp)
- Proxy worker pattern

---

# Use Cases

This type of automation can be applied to:

- Batch geocoding large datasets
- Mapping adresses or assets
- Operational dashboards
- Territory analysis
- Logistics routing preparation
- Data enrichment workflows

---

# Why Two Implementations?

This project compares:

| Google Maps | Nominatim |
|-------------|------------|
| Commercial API | Open-source API |
| Requires API key | Requires proxy identification |
| Paid beyond quota | Free (policy compliant use) |
| Direct integration | Layered architecture |

The comparison demonstrates different architectural approaches and trade-offs.

---

# Notes

- API keys and sensitive identifiers are not included.
- Worker implementation is provided as a template.
- Designed for educational and portfolio purposes.

---

# Author

Developed as a portfolio project focused on geospatial automation and API integration using Google Workspace tools.
