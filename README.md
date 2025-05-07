# DataSpace
A self-contained, self-modifying, self-replicating HTML-embedded file storage system with zero dependencies and dynamic document modification capabilities.

## About This Repository
This repository serves as the public information hub and access point for the DataSpace technology. The core source code for DataSpace is maintained in a private repository to protect our proprietary patent-pending file storage and sharing technology. This repository is ONLY for remote access and information on DataSpace. For licensing inquiries regarding the DataSpace technology, please contact edan@analyticintelligencesolutions.com.

## Try DataSpace
Visit https://edan-ais.github.io/DataSpace/ to experience the technology directly in your browser!

## Patent Notice
The DataSpace technology is patent-pending under provisional application number [APPLICATION NUMBER] filed with [PATENT OFFICE] on [FILING DATE].

This repository provides a demonstration implementation with limited usage rights ONLY. This code is NOT available for commercial use, modification, or redistribution without explicit licensing permission.

## What is DataSpace?
DataSpace is a self-modifying document that functions as its own file storage system. Unlike traditional client-server solutions that require backend infrastructure, DataSpace exists as a single HTML file that can be transmitted through standard file-sharing methods while preserving all embedded content. Users can access files with any standard web browser without additional software installation, account creation, or active network connection. This implementation eliminates dependencies on external services by internalizing all storage and retrieval functionality within the document itself.

# Technical Architecture
## Core Technology Stack
DataSpace implements file storage through document self-modification rather than client-server communication. The codebase consists of vanilla HTML, CSS, and JavaScript without external frameworks or dependencies. The system utilizes the browser-native storage APIs IndexedDB and localStorage for temporary data caching. File processing follows a defined pipeline: input files are read as ArrayBuffers, converted to Base64-encoded strings, and stored initially in IndexedDB. For persistent storage, DataSpace either embeds these encoded strings as meta tags in the HTML document structure or compresses them into URL parameters for transmission.

The security implementation leverages inherent properties of the encoding process and browser security models. Base64 encoding transforms binary data into an ASCII string representation, which browsers interpret as data rather than executable instructions. The system incorporates validation checks during encoding and decoding operations to verify data integrity and reject malformed content. The client-side execution model isolates all processing within the browser sandbox, eliminating server-side attack surfaces. Data remains local to the user's device until explicit export operations are performed, with only the document owner retaining access to the modified file.

## Key Features and User Benefits
DataSpace provides file management functionality through a browser-based interface. The system supports multiple file formats with type-specific preview handlers that render content without external applications. The technical architecture offers specific operational advantages. The self-contained structure eliminates external dependencies, providing consistent functionality regardless of network connectivity. Data remains under user control with no automatic transmission to external systems. The removal of server infrastructure requirements reduces implementation complexity while maintaining core file management capabilities. The browser-based execution environment ensures cross-platform compatibility without requiring platform-specific installations.

## Future Development
Browser storage limitations could eventually constrain capacity, so compression techniques and strategic partitioning will be implemented in the core process flow to help overcome these boundaries. The current design creates multiple file copies to ensure everything stays personal to the individual's computer, but manual file moving and deletion will quickly become impractical for collections of small, rapid changes. The intended fix is to create a virtual file system interface (potentially a parallel vector version of the computer's filing system) to automatically handle document deletion and replacement. To avoid any accidental deletion through the automated system, documents will be kept in a document purgatory in DataSpace until a certain amount of time has passed or you delete them, whichever comes first. The next full iteration of DataSpace will add support for more file types to have enhanced preview and editing capabilities, particularly being able to interact with content like video games and videos directly within the document. The following release should add support for global, online sharing of documents and files, not just peer-to-peer sharing, to allow for more collaborative document editing, offline knowledge bases, and portable development environments. We envision DataSpace becoming the standard for specialized document sharing in areas like education, healthcare documentation, creative media, and secure information exchange.

## Development
Clone the repository to your local machine using Git. No build process is required - simply serve the files locally using a basic HTTP server. Access the development version at localhost:8080 to start exploring the revolutionary capabilities of the DataSpace technology.

## System Requirements
For optimal performance, DataSpace requires a modern browser (Chrome 76+, Firefox 69+, Safari 14+), JavaScript enabled with IndexedDB and localStorage access, and at least 5MB of available browser storage.

## Legal Information
For detailed legal information, please refer to our License, Terms of Use, and Privacy Policy documents.
