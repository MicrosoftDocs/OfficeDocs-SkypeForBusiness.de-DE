---
title: Installieren des Pakets für die Abwärtskompatibilität mit WMI
TOCTitle: Installieren des Pakets für die Abwärtskompatibilität mit WMI
ms:assetid: 38797fbd-06a0-4008-b099-158e7b5d7703
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204816(v=OCS.15)
ms:contentKeyID: 49293689
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Installieren des Pakets für die Abwärtskompatibilität mit WMI

 

_**Letztes Änderungsdatum des Themas:** 2012-10-02_

Wenn Sie versuchen, den Zusammenführungs-Assistenten des Topologie-Generators auszuführen, ohne das WMI-Abwärtskompatibilitätspaket zu installieren, tritt der folgende Fehler auf:

![WMI-Fehlermeldung](images/JJ204816.a007d2f2-fc85-430c-91eb-382b032469af(OCS.15).jpg "WMI-Fehlermeldung")

Wenn Sie versuchen, das **Merge-CsLegacytopology** -Cmdlet ohne Installieren des WMI-Abwärtskompatibilitätspakets auszuführen, erhalten Sie den folgenden Fehler:

![Windows PowerShell: WMI-Anbieterfehler](images/JJ204816.c510824e-1807-4c7e-bb28-c6cfea2eac1d(OCS.15).jpg "Windows PowerShell: WMI-Anbieterfehler")

So installieren Sie das WMI-Abwärtskompatibilitätspaket

1.  Navigieren Sie vom Installationsdatenträger zu **\\SETUP\\AMD64\\SETUP\\OCSWMIBC.MSI** .

2.  Installieren Sie **OCSWMIBC.MSI** .
    

    > [!IMPORTANT]
    > <STRONG>OCSWMIBC.msi</STRONG> muss auf dem Computer installiert werden, auf dem der Zusammenführungs-Assistent des Topologie-Generators ausgeführt wird. Es wird jedoch empfohlen, <STRONG>OCSWMIBC.msi</STRONG> auf allen Front-End-Servern in der Topologie auszuführen.

    

    > [!IMPORTANT]
    > <STRONG>OCSWMIBC.msi</STRONG> kann auf jedem Computer in der Domäne installiert werden, auf dem die Hauptkomponenten von Lync Server 2013 und die Lync Server 2013-Verwaltungsshell installiert sind und der Zugriff auf die Office Communications Server 2007 R2-Topologie hat (WMI-Anbieter für Active Directory-Domänendienste (AD DS) und SQL&nbsp;Server).


