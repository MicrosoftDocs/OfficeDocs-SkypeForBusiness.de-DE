---
title: 'Lync Server 2013: Vorbereiten der Umgebung für VDI'
TOCTitle: Vorbereiten der Umgebung für VDI
ms:assetid: a3ec2e13-1a73-4b1c-a54a-8db7d4cd50f9
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205154(v=OCS.15)
ms:contentKeyID: 49294968
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vorbereiten der Lync Server 2013-Umgebung für VDI

 

_**Letztes Änderungsdatum des Themas:** 2013-02-22_

Für die Vorbereitung der Umgebung für das VDI-Plug-In für Lync muss der Administrator die folgenden Schritte ausführen.

1.  Stellen Sie in Lync Server 2013 sicher, dass "EnableMediaRedirection" für alle VDI-Benutzer auf TRUE festgelegt ist. Genauere Informationen finden Sie in den Hilfethemen zum [New-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClientPolicy)-Cmdlet und [Set-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPolicy)-Cmdlet.

2.  Installieren Sie auf dem Rechenzentrumcomputer den Lync 2013-Client auf allen virtuellen Computern.

3.  Installieren Sie auf den lokalen Computern das VDI-Plug-In für Lync.

