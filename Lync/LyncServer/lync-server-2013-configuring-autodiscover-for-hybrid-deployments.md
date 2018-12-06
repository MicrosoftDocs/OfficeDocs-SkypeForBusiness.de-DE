---
title: Konfigurieren der AutoErmittlung für Hybridbereitstellungen
TOCTitle: Konfigurieren der AutoErmittlung für Hybridbereitstellungen
ms:assetid: ca605e62-181c-42ca-80a1-e37e610f8277
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ945653(v=OCS.15)
ms:contentKeyID: 52056455
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren der AutoErmittlung für Hybridbereitstellungen

 

_**Letztes Änderungsdatum des Themas:** 2012-12-12_

Hybridbereitstellungen sind Konfigurationen, in denen sowohl der Microsoft Lync Online-Clouddienst als auch die lokale Bereitstellung verwendet werden. Bei diesem Typ Konfiguration muss der AutoErmittlungsdienst herausfinden können, wo sich der Benutzer gegenwärtig befindet. Das heißt, die AutoErmittlung hilft, das Benutzerkonto sowie den Standort des Servers zu finden, der das Konto des Benutzers hostet, egal, ob dies die lokale Bereitstellung oder die Skype for Business Online-Bereitstellung ist.

Ein Beispiel: Wenn das Konto eines Benutzers auf einem Server in Skype for Business Online gehostet wird, erfolgt die Lokalisierung des Benutzers im folgenden Prozess, der auch als *Erkennbarkeit* bezeichnet wird:

  - Der Benutzer versucht, eine Verbindung zur lokalen Bereitstellung herzustellen, **contoso.com**.

  - Der Verbindungsversuch wird an **lyncdiscover.contoso.com** gesendet, den DNS-Namen, der dem AutoErmittlungsdienst zugeordnet wurde.

  - Die AutoErmittlung führt eine Weiterleitung an den angenommenen Registrierungsstellenpool in der lokalen Bereitstellung von "contoso.com" durch und erhält Informationen zu dem tatsächlichen in Skype for Business Online gehosteten Homeserver des Benutzers. Anschließend sendet die AutoErmittlung dem Benutzer eine Weiterleitung an den Online-AutoErmittlungsdienst von **lync.com**.

  - Der Benutzer versucht, eine Verbindung zum Online-AutoErmittlungsdienst von **lync.com** herzustellen und kann das Konto des Benutzers auf dem Homeserver des Benutzers auffinden.

Damit Clients die Bereitstellung ermitteln können, in der sich der Homeserver des Benutzers befindet, müssen Sie den AutoErmittlungsdienst mit einer neuen URL (Uniform Resource Locator) konfigurieren. Führen Sie dazu folgende Schritte aus.

## Konfigurieren der AutoErmittlung für hybride Bereitstellungen

1.  Im Thema [Anforderungen für den AutoErmittlungsdienst für Lync Server 2013](lync-server-2013-autodiscover-service-requirements.md) verwenden Sie **Get-CsHostingProvider** zum Abrufen des Wertes des **ProxyFQDN**-Attributs.

2.  Geben Sie in der Lync Server-Verwaltungsshell Folgendes ein:
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodisccoverservice.svc/root
    
    Hierbei wird **\[identity\]** durch den Domänennamen des freigegebenen SIP-Adressraums ersetzt.

## Siehe auch

#### Weitere Ressourcen

[Get-CsHostingProvider](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsHostingProvider)  
[Set-CsHostingProvider](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsHostingProvider)

