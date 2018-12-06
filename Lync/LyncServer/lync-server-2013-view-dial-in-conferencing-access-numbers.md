---
title: Anzeigen von Zugriffsnummern für Einwahlkonferenzen
TOCTitle: Anzeigen von Zugriffsnummern für Einwahlkonferenzen
ms:assetid: 41a7dfb4-0c89-4650-b61b-0e1bf875c62b
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688037(v=OCS.15)
ms:contentKeyID: 49890723
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anzeigen von Zugriffsnummern für Einwahlkonferenzen

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

In Systemsteuerung für Lync Server 2013 stellen Sie Benutzern Einwahl-Zugriffsnummern zur Verfügung, sodass sie einer Besprechung als externer Teilnehmer beitreten können.

## So zeigen Sie Zugriffsnummern für die Einwahl an

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Konferenz** und dann auf **Zugriffsnummer für Einwahl**.

4.  Klicken Sie auf der Seite **Zugriffsnummer für Einwahlkonferenz** auf die Zugriffsnummer, die Sie anzeigen möchten.

5.  Aktivieren Sie unter **Bearbeiten** das Kontrollkästchen **Details anzeigen**.

## Anzeigen von Zugriffsnummern für Einwahlkonferenzen mithilfe der Lync Server PowerShell-Cmdlets

Zugriffsnummern für Einwahlkonferenzen können auch mit Lync Server PowerShell und dem Cmdlet "Get-CsDialInConferencingAccessNumber" angezeigt werden. Dieses Cmdlet kann entweder aus der Verwaltungsshell für Lync Server 2013 oder aus einer Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Anzeigen der Konfigurationsinformationen für den SIP-Trunk

  - Um Informationen über all Ihre Zugriffsnummern für Einwahlkonferenzen anzuzeigen, geben Sie folgenden Befehl in die Lync Server-Verwaltungsshell ein, und drücken Sie die EINGABETASTE:
    
        Get-CsDialInConferencingAccessNumber
    
    Die zurückgegebenen Informationen entsprechen in etwa folgendem Beispiel:
    
        Identity           : CN={20ca8dc8-5ff8-41f4-b5bb-22ba9972ae2e},
                             CN=Application Contacts,CN=RTCService=Services,
                             CN=Configuration,DC=litwareinc,DC=com
        PrimaryUri         : sip:testnumber@litwareinc.com
        DisplayName        : Test
        DisplayNumber      : 1-425-555-1019
        LineUri            : tel:+14255551019
        PrimaryLanguage    : en-US
        SecondaryLanguages : {}
        Pool               : atl-cs-001.litwareinc.com
        HostingProvider    :
        Regions            : {US}

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsDialInConferencingAccessNumber).

