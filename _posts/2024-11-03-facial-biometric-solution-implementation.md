---
title: 'Facial Biometric Solution Implementation '
published: true
date: '2024-11-04'
---
**AeroPass** is a facial biometric authentication solution designed to streamline the boarding process for passengers at airports. With AeroPass, users can enroll in the comfort of their homes, authenticate their identities securely, and ensure a smooth experience at the boarding gate.

![https://raw.githubusercontent.com/bhishekarora/bhishekarora.github.io/master/img/aeropasslogo.png](https://raw.githubusercontent.com/bhishekarora/bhishekarora.github.io/master/img/aeropasslogo.png)

## Products supporting this implementation 
![https://raw.githubusercontent.com/bhishekarora/bhishekarora.github.io/master/img/modules.png](https://raw.githubusercontent.com/bhishekarora/bhishekarora.github.io/master/img/modules.png)

## Key Features

*   **Remote Enrollment**: Users can enroll from their mobile devices, allowing them to verify their identity and authenticate before arriving at the airport.
    
*   **Secure Identity Verification**: Integration with identity verification systems, like Aadhaar in India, allows users to authenticate with mobile OTP.
    
*   **Liveness Detection**: Uses multi-frame detection and facial vector algorithms to verify that a live person is taking the selfie, enhancing security.
    
*   **Token-Based Authentication**: Once authenticated, AeroPass generates a unique token that can be used for boarding.
    
*   **Integration with Airport Boarding Systems**: Connects with backend AeroPass servers installed at the airport, allowing for a seamless transition through boarding gates.
    

## How It Works

### Step 1: User Enrollment at Home

1.  **Download the App**: Users start by downloading the AeroPass app on their mobile phones.
    
2.  **Identity Verification**: Users are prompted to authenticate with a recognized identity provider, such as Aadhaar in India. This is accomplished by entering a mobile OTP for added security.
    
3.  **Details Confirmation**: Once the OTP is confirmed, the app retrieves and displays identity information (name, date of birth, etc.) for the user to verify.
    

### Step 2: Liveness Check and Selfie Capture

1.  **Selfie Capture**: After confirming identity details, the app prompts the user to take a selfie.
    
2.  **Liveness Detection**: Using multi-frame analysis and facial vector algorithms, AeroPass checks for signs of a live human (like eye blinks) to ensure security.
    
3.  **Selfie Storage**: Once liveness is confirmed, selfie is matched with aadhar image using facenet 512 (Declared score 99 % on model), the app securely saves the selfie with token for future use.
    

### Step 3: Boarding Pass Upload

1.  **Boarding Pass Submission**: Before reaching the airport, the user uploads their boarding pass to the app.
    
2.  **Data Transmission to Backend**: The AeroPass app sends the userâs verified selfie, facial data, and PNR details to the backend AeroPass server for verification to DCS and store in Aero pass platform Server.
    

### Step 4: Airport Boarding Process

1.  **Token-Based Authentication at Boarding Gates**: At the airport, the AeroPass system integrated with boarding gates validates the token, allowing the user to pass through after facials are matched via the Aeropass Facial Match Server
    
2.  **Seamless Experience**: Users can now proceed through the boarding gate using facial recognition, making the entire process faster and more convenient.
    

## Technical Architecture

1.  **Frontend (Mobile App)**:
    
    *   Hybrid **Android/ios**.
        
    *   Integrates with identity verification APIs (e.g., Aadhaar ).
        
    *   Captures frames for liveness detection and facial vectors(4096) analysis of live frames to detect liveness via the Aeropass Liveness Server
        
2.  **Backend (AeroPass Server)**:
    
    *   Receives data from the app, including facial recognition data and PNR details from BP scan.
        
    *   Validates user identity at the boarding gates in coordination with the airport DCS systems.
      
    *   Exposes APIs for Aero pass gate controller to fetch facial data from PNR queries via BP QR scan.
        
3.  **Identity Verification**:
    
    *   Uses **OTP-based verification** for Aadhaar.
        
    *   Displays fetched identity data for user confirmation.
        
4.  **Liveness Detection**:
    
    *   Implements multi-frame detection to verify the user's live presence.
        
    *   Applies facial vector algorithms (EAR ratios on multiple frames) to authenticate the user in real-time.
        

## Future Enhancements

*   **Expansion to More Identity Solutions**: Plan to integrate with other govt identity providers.
    
*   **Real-Time Liveness Feedback**: Enhance real-time feedback for improved liveness detection accuracy.
    
*   **Integration with Airline Systems**: More connectors to work with SITA/Amadeus systems
    
## Egate Hardware (Controlled via Egate Controller Module)

- **MVP Version (Ready) - DIY <12 Volts**: Gate(fabric)/SOC/LEDs/LCD/USBcam/Sensors/Servos 
- **Lite Version (In Prg.) - DIY 220 Volts Version** : Gate (metal/wood housing)/BLDC24v/Switches/Relays/Leds/LCD/USBcam/ProximitySensor
- **Commercial Version DIY (Can be built) 220V** : Gate(Steel body housing from Indiamart) , others peripherals and motors will be assembled and soldered on SOC as for above versions , minor welding might be required for this.
- **Commerical Version off the shelf** : Gunnebbo/Kaba/Indiamart gates can be integrated with solution with gates starting at 40k INR/$500 at Indiamart.

> Peripherals  controlled via Aero pass gate controller and integrated with Aero pass Server

AeroPass enables travelers to experience a fast, secure, and seamless airport boarding process by using cutting-edge biometric technology. By leveraging at-home enrollment, secure identity verification, and airport-integrated boarding systems, AeroPass enhances both convenience and security.

_For more details and the complete codebase, visit_ [GitHub Repository](https://github.com/bhishekarora/aeropass)_._



# Product/Module links
- Aeropass Server [https://github.com/bhishekarora/AeroPass-Server](https://github.com/bhishekarora/AeroPass-Server)
- Aeropass Gate Controller [https://github.com/bhishekarora/AeroPass-GateController](https://github.com/bhishekarora/AeroPass-GateController)
- Aeropass App [https://github.com/bhishekarora/AeroPass-App](https://github.com/bhishekarora/AeroPass-App)
- Aeropass Liveness Server[https://github.com/bhishekarora/Aeropass-Liveness-Detection-Server](https://github.com/bhishekarora/Aeropass-Liveness-Detection-Server)
- Aeropass Facial Match Server[https://github.com/bhishekarora/Aeropass-facial-match-server](https://github.com/bhishekarora/Aeropass-facial-match-server)
