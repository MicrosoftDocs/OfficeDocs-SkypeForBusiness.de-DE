---
title: Erste Schritte vor dem Migrieren von Benutzern von Lync Online zur lokalen Lync-Bereitstellung
TOCTitle: Erste Schritte vor dem Migrieren von Benutzern von Lync Online zur lokalen Lync-Bereitstellung
ms:assetid: 98245b04-ded4-4186-8da3-ba1c554b5c39
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn689118(v=OCS.15)
ms:contentKeyID: 62247568
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erste Schritte vor dem Migrieren von Benutzern von Lync Online zur lokalen Lync-Bereitstellung

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Bevor Sie beginnen, Lync Online-Benutzer zu Ihrer lokalen Umgebung zu verschieben, überprüfen Sie, ob alle folgenden Punkte zutreffen:

  - Ihre lokale Lync Server-Bereitstellung muss vollständig bereitgestellt und validiert sein. Weitere Informationen finden Sie unter [Bereitstellen von Lync Server 2013](lync-server-2013-deploying-lync-server.md).

  - Ihr Lync Online-Mandant muss für den Remote-PowerShell-Zugriff aktiviert sein.
    
    Installieren Sie dafür zunächst das Skype for Business Online-Modul für Windows PowerShell, das Sie unter der folgenden Adresse erhalten: [http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911).
    
    Nach der Installation des Moduls können Sie eine Remotesitzung einrichten, indem Sie die folgenden Cmdlets in die Lync Server-Verwaltungsshell eingeben:
    
        Import-Module LyncOnlineConnector

       &nbsp;
    
        $cred = Get-Credential

       &nbsp;
    
        $CSSession = New-CsOnlineSession -Credential $cred

       &nbsp;
    
        Import-PSSession $CSSession -AllowClobber
    
    Weitere Informationen zum Einrichten einer Remote-PowerShell-Sitzung mit Skype for Business Online finden Sie unter [Herstellen der Verbindung zu Lync Online mit Windows PowerShell](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
  
    Weitere Informationen zur Verwendung des Skype for Business Online PowerShell-Moduls finden Sie unter [Verwenden von Windows PowerShell zum Verwalten von Lync Online](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

  - Lync Online muss für den freigegebenen SIP-Adressbereich konfiguriert sein. Starten Sie dafür zunächst eine Remote-Powershell-Sitzung mit Lync Online. Führen Sie dann das folgende Cmdlet aus:
    
        Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True

Wenn Sie diese Schritte abgeschlossen haben, können Sie mit [Migrieren von Lync Online-Benutzern zur lokalen Lync-Bereitstellung](lync-server-2013-migrating-lync-online-users-to-lync-on-premises.md) fortfahren.

