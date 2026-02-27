Project Overview

This project focused on improving the geo-coordinate extraction system within DBpedia’s Extraction Framework. The existing system faced major accuracy issues, particularly for Southern Hemisphere locations, where longitude values were incorrectly stored with positive signs. Additionally, limited support for multilingual coordinate templates resulted in parsing failures and missing geographic data.

The goal was to significantly improve coordinate precision, expand language coverage, and enhance debugging capabilities for developers working with the extraction server.

Problem Statement

Southern Hemisphere coordinates incorrectly parsed (~60% accuracy)

Only 5 languages supported for coordinate templates

Rigid parsing logic failed for diverse international formats

No support for individual extractor debugging on the mapping server

PR #779: Enhanced Geo-Coordinate Parsing & Precision

Status: ✅ Approved & Ready for Merge
Impact Area: Core Data Parser

Key Improvements

Fixed hemisphere sign handling logic

Expanded language support from 5 to 19 languages

Added native character recognition (Arabic, Chinese, Japanese, Korean, etc.)

Improved regex patterns for 25+ coordinate template formats

Implemented BigDecimal precision for accurate coordinate calculations

Added comprehensive validation and error handling

Results

Southern Hemisphere accuracy improved from ~60% to ~95%

Parse success rate increased from 75% to 94%

~50,000+ geographic entities corrected

Reduced test failures from 25 errors to 0 errors

PR #780: Enable Single-Extractor Execution on Mapping Server

Status: ✅ Approved & Ready for Merge
Impact Area: Server Debugging & Performance

Key Improvements

Implemented intelligent caching using Guava LoadingCache

Reduced extractor initialization time by ~90%

Added dynamic dropdown for selecting individual extractors

Centralized configuration management

Improved logging and error monitoring

Results

90% faster extractor initialization

Better debugging support for developers

Improved maintainability and modular server design

Performance Improvements Summary
Metric	Before	After	Improvement
Southern Hemisphere Accuracy	~60%	~95%	+58%
Parse Success Rate	75%	94%	+25%
Extractor Initialization	Every Request	Cached	~90% Faster
Language Support	5	19	280% Increase
Code Quality & Verification

1,378 lines added, 226 lines removed

9 core framework files modified

SonarQube Quality Gate Passed

All CI/CD checks successful

Approved by project maintainers

Technical Skills Developed

Advanced Scala development and debugging

Multi-language parsing logic design

Regex optimization for international data formats

Performance tuning using caching strategies

Maven build and testing workflows

Production-grade unit and integration testing

Impact

This project significantly improves DBpedia’s geographic data reliability and international coverage. The enhanced parser ensures accurate representation of global locations, while the new server debugging capabilities empower contributors to test and validate extractors more efficiently.

Both pull requests are approved and production-ready, directly benefiting the DBpedia ecosystem and thousands of downstream applications that rely on accurate geographic data.