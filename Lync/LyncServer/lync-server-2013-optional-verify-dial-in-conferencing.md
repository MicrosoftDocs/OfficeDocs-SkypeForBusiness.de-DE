---
title: 'Lync Server 2013: (Optional) Überprüfen von Einwahlkonferenzen'
TOCTitle: '(Optional) Überprüfen von Einwahlkonferenzen '
ms:assetid: 3e2b4220-8fb3-442f-98b1-78447adb321f
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425905(v=OCS.15)
ms:contentKeyID: 49293773
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# (Optional) Überprüfen von Einwahlkonferenzen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2011-01-21_

Sie müssen die folgenden Aufgaben ausführen, um sicherzustellen, dass die Webseite mit den Einstellungen für Einwahlkonferenzen und die Zugriffsnummern für die Einwahl ordnungsgemäß funktionieren:

  - Testen Sie die Webseite mit Einstellungen für Einwahlkonferenzen, indem Sie sich über die einfache URL anmelden.

  - Testen Sie die Zugriffsnummern für einen bestimmten Pool, indem Sie das weiter unten in diesem Thema gezeigte Skript ausführen. Dieses Skript simuliert Anrufe bei Zugriffsnummern. Sie benötigen zur Verwendung dieses Skripts die SIP-Adresse und Anmeldeinformationen für einen Unified Communications-Client (UC), der im angegebenen Pool gehostet wird.

Dieser Schritt ist optional.

## So testen Sie Zugriffsnummern für einen spezifischen Pool

1.  Melden Sie sich beim Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle **Cs-ServerAdministrator** oder **CsAdministrator** an.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Führen Sie den folgenden Befehl an der Eingabeaufforderung aus:
    
        $credentials = Get-Credential
           User name:  testuser1@contoso.com
           Password:   ********
        Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
    
    In den Berichtergebnissen wird der Test entweder als erfolgreich oder mit Fehlern angezeigt, zusammen mit spezifischen Diagnoseinformationen. Mit dem Flag "-Verbose" werden detailliertere Informationen bereitgestellt, z. B. die Anzahl von ermittelten Zugriffsnummern sowie weitere Informationen zu den Zugriffsnummern.

