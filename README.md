## Analysis

**UxPlay Double Free Vulnerability**

Project: UxPlay

Version Affected: 1.72 (Snap-distributed binary)

Reported: 2025-08-17

Vulnerability Type: **Double Free / Memory Corruption**

## Description
UxPlay 1.72, an open-source AirPlay mirroring server, contains a double free vulnerability in its RTSP request handling. A specially crafted RTSP TEARDOWN request can trigger multiple calls to free() on the same memory address, potentially causing:

- Application crash (denial of service)

- Possible memory corruption leading to remote code execution.


CVSS metrics 

Attack Vector (AV): Network (N)

- The vulnerability can be triggered by sending a crafted RTSP request over the network.

Attack Complexity (AC): Low (L)

- No special conditions required other than sending the malformed request.

Privileges Required (PR): None (N)

- The attacker does not need any privileges to exploit this issue.

User Interaction (UI): None (N)

- No user interaction is required.

Scope (S): Unchanged (U)

- The vulnerability affects only UxPlay, no impact crosses into other components.

Confidentiality (C): Low (L)

- Crash may not directly expose sensitive data, but memory corruption could potentially leak information.

Integrity (I): Low (L)

- Memory corruption could allow modification of internal memory, but no confirmed full arbitrary write.

Availability (A): High (H)

- The service crashes reliably, causing denial of service.

