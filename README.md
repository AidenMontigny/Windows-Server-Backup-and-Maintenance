<h1> Windows Server Backup and Restoring </h1>

<h2>Description</h2>
This repository contains the lab exercises performed for the "Backing Up and Restoring System Files" project, which demonstrates the process of securing and restoring system files using Windows Server Backup tools. The project highlights the critical importance of regular backups for data integrity, disaster recovery, and cybersecurity. It includes detailed screenshots and steps for performing system maintenance tasks such as using the dism /Online /Cleanup-Image /Restorehealth, sfc /scannow, and chkdsk C:/f commands to check and repair the system health. Additionally, the project covers using the Windows Server Backup tool to create a full system backup and testing its functionality by restoring a specific folder after it was deleted. The project emphasizes the necessity of maintaining secure backups to protect against data loss from hardware failures, cyberattacks, or accidental deletions. The exercises also demonstrate how to use backup tools, analyze system events, and validate the success of restoration. This project serves as a valuable reference for cybersecurity professionals and IT administrators, ensuring data safety, system recovery, and business continuity in critical environments.
<br />

<h2>Languages and Utilities Used</h2>

- <b> Command Line </b> 
- <b> Windows Server Backup </b>
- <b> Event Viewer </b>
- <b> Powershell </b>

<h2>Environments Used </h2>

- <b> Windows Server 2022 </b>

<h2>Project walk-through:</h2>
<p align="left">
Executed the dism /Online /Cleanup-Image /Restorehealth command to initiate a system image repair using Deployment Image Servicing and Management (DISM).  <br/><br/>
  <img src="Screenshot 2025-04-19 144313.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
  <br/>
<p align="left">
an the sfc /scannow command to initiate the System File Checker tool, which scans all protected system files and replaces corrupted or missing files with known good versions from the Windows cache. <br/><br/>
  <img src="Screenshot 2025-04-19 144322.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
  <br/>
  <p align="left">
Executed the chkdsk C: /f command to check the file system and file system metadata on the C: drive for logical errors. The /f parameter ensures that any detected issues are automatically fixed. <br/><br/>
  <img src="Screenshot 2025-04-19 144331.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
  <br/>
    <p align="left">
Restarted the system to complete the disk error-checking process initiated by the chkdsk command, as certain repairs require a reboot to be applied successfully. <br/><br/>
  <img src="Screenshot 2025-04-19 144341.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
  <br/>
      <p align="left">
Used Event Viewer to verify the results of the chkdsk operation by reviewing logs under Wininit. This step confirms whether file system repairs were successfully completed during system startup. <br/><br/>
  <img src="Screenshot 2025-04-19 144349.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
  <br/>
        <p align="left">
Reviewed the results in Event Viewer to validate system diagnostics and confirm successful execution of maintenance tasks such as chkdsk. <br/><br/>
  <img src="Screenshot 2025-04-19 144401.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
  <br/>
          <p align="left">
Created the Special Customers Montigny folder as part of the project setup, with plans for later recovery during the process. <br/><br/>
  <img src="Screenshot 2025-04-19 144410.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
  <br/>
            <p align="left">
Added a file containing the names of the Special Customers to the Special Customers Montigny folder, preparing it for later recovery during the project. <br/><br/>
  <img src="Screenshot 2025-04-19 144416.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
  <br/>
              <p align="left">
Installed Windows Server Backup to enable efficient backup and recovery management for the server environment. <br/><br/>
  <img src="Screenshot 2025-04-19 144425.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
  <br/>
                <p align="left">
Shared the Backups file and provided the network path for easy access and management of backup files across the network. <br/><br/>
  <img src="Screenshot 2025-04-19 144434.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
  <br/>
                  <p align="left">
Confirmed the successful completion of the backup process, ensuring that all selected data was securely stored for recovery purposes.<br/><br/>
  <img src="Screenshot 2025-04-19 144444.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
  <br/>
                    <p align="left">
Verified that the Special Customers Montigny file was moved to the Recycle Bin, indicating it was flagged for potential recovery. <br/><br/>
  <img src="Screenshot 2025-04-19 144458.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
  <br/>
                      <p align="left">
Confirmed the permanent deletion of the Special Customers Montigny file from the Recycle Bin, ensuring it was fully removed from the system. <br/><br/>
  <img src="Screenshot 2025-04-19 144506.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
  <br/>
                        <p align="left">
Initiated the Recovery Wizard and selected the Special Customers Montigny file for recovery, preparing to restore it to its original location. <br/><br/>
  <img src="Screenshot 2025-04-19 144513.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
  <br/>
                          <p align="left">
Confirmed the successful completion of the recovery process, with the Special Customers Montigny file restored to its original location. <br/><br/>
  <img src="Screenshot 2025-04-19 144521.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
  <br/>
                            <p align="left">
Verified that the Special Customers Montigny file was successfully restored and is now back in the Documents folder. <br/><br/>
  <img src="Screenshot 2025-04-19 144528.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
  <br/>

                              
<h2>Write Up</h2>

<p><u> Performing Backups and Restoring Data </u></p>
<p>To perform backups and restore data on a system, it requires a whole process is required. Firstly, it is crucial to secure multiple copies of important data in physical or virtual locations to guarantee the recovery of data in case of hardware failure, data corruption, or cyberattack (GeeksforGeeks, 2021). I would do a full backup, which saves all files and folders, however, it does require more time and storage. I also personally store my backup on a USB drive and lock it in my safe to ensure that it is secure from theft, fires, and much more. If I ever needed to back up my computer for any reason, all I would have to do is insert the USB drive into my computer, locate the backed-up files I want to restore, and add them back to my computer. Overall, this process is simple, but it ensures that no matter what, my computer and data are safeguarded from any element or malicious actor. </p>

<p><u> Backup Testing Process </u></p>
<p>The purpose of this assignment was to perform a full backup and verify its functionality by restoring deleted content during routine maintenance. I began by creating a folder named "Special Customers and Montigny in the Documents folder, which contained a text file named "Special Customers" with the names Mary Smith, Thomas Green, and Taylor Jones. After saving this file, I tried to proceed with the full backup of the server using the Windows Server Backup tool, ensuring that all files and system configurations were backed up. To test the backup’s integrity, I was supposed to delete the "Special Customers" folder, simulating an accidental data loss scenario. Then, using the backup tool, I was supposed to restore the folder from the full backup, successfully returning it to its original location. This would confirm the backup’s functionality and reliability. </p>

<p><u> Importance of Backups and Restoration for Cybersecurity Professionals </u></p>
<p>Backups and restoration are a key part of cybersecurity, as they serve as the foundation of disaster recovery and business continuity. Regular backups can aid in protecting organizations against permanent data loss due to deletion, hardware malfunctions, and even cyberattacks (Rocherston, 2023). They also aid in ensuring data integrity by enabling the system to be restored to its original state. By having effective backup plans, organizations can ensure that they minimize downtimes, allowing them to go back to their day-to-day activities quickly after an issue has occurred. Backups and restorations also aid organizations in keeping up with their compliance requirements, as they will be prepared for any audit or legal obligations within their systems. Additionally, by mitigating the financial impact of cyberattacks, such as avoiding ransom payments, well-executed backup strategies significantly reduce recovery costs. Key practices include automating backups, maintaining on-site and off-site copies, encrypting data, and regularly testing restoration procedures, all of which contribute to data protection and operational continuity. </p>

<p><u> References </u></p>
<p>GeeksforGeeks. (2021, June 16). Backup and restore. GeeksforGeeks. https://www.geeksforgeeks.org/backup-and-restore/ </p>
<p>Rocheston. (2023, May 17). The importance of backup and disaster recovery in cybersecurity. Information Age. https://u.rocheston.com/the-importance-of-backup-and-disaster-recovery-in-cybersecurity/#:~:text=Backup%20and%20disaster%20recovery%20are%20critical%20components%20of,along%20with%20best%20practices%20for%20implementing%20effective%20strategies. </p>
