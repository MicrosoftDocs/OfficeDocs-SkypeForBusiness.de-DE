---
title: Löschen von vorhandenen Webdienst-Konfigurationseinstellungen
TOCTitle: Löschen von vorhandenen Webdienst-Konfigurationseinstellungen
ms:assetid: c2b96f4c-4b07-48e6-9ca6-55bc0e0cf5a1
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg182582(v=OCS.15)
ms:contentKeyID: 49295316
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Löschen von vorhandenen Webdienst-Konfigurationseinstellungen

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Führen Sie die folgenden Schritte aus, um eine Webdienstrichtlinie zu löschen.

## So löschen Sie eine Webdienstrichtlinie

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsServerAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer des Netzwerks an, in dem Sie Lync Server 2013 bereitgestellt haben.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **Webdienst**.

4.  Geben Sie auf der Seite **Webdienst** im Suchfeld Teile oder den vollständigen Namen der Richtlinie ein, die Sie löschen möchten.

5.  Klicken Sie in der Richtlinienliste auf die gewünschte Richtlinie, klicken Sie auf **Bearbeiten** und dann auf **Löschen**.

6.  Klicken Sie auf **OK**.

## Löschen neuer Konfigurationseinstellungen für Webdienste mithilfe der Lync Server-Verwaltungsshell-Cmdlets

Konfigurationseinstellungen für Webdienste können Sie auch mit der Lync Server-Verwaltungsshell und dem **Remove-CsWebServiceConfiguration**-Cmdlet löschen. Dieses Cmdlet können Sie über die Verwaltungsshell für Lync Server 2013 oder in einer Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## So löschen Sie bestimmte Konfigurationseinstellungen für Webdienste

  - Mit dem folgenden Befehl werden die Webdienstsicherheitseinstellungen für den Standort "Redmond" entfernt:
    
        Remove-CsWebServiceConfiguration -Identity "site:Redmond"

## So löschen Sie alle auf Standortebene angewendeten Konfigurationseinstellungen für Webdienste

  - Mit dem folgenden Befehl werden alle auf Dienstebene angewendeten Webdienstsicherheitseinstellungen entfernt:
    
        Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration

## So löschen Sie alle Konfigurationseinstellungen für Webdienste, die die Zertifikatauthentifizierung erlauben

  - Mit dem folgenden Befehl werden alle Webdienstsicherheitseinstellungen entfernt, die die Verwendung der Zertifikatauthentifizierung erlauben:
    
        Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration

Ausführliche Informationen finden Sie unter [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsWebServiceConfiguration).

## Siehe auch

#### Weitere Ressourcen

[Konfigurieren der Sicherheit](lync-server-2013-configuring-authentication-in-the-lync-server-control-panel.md)

