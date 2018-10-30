---
title: Hybriddomäne oder geteilte Domäne – AutoErmittlung
TOCTitle: Hybriddomäne oder geteilte Domäne – AutoErmittlung
ms:assetid: c855bcc5-b656-4d2d-92d6-f016f2797d3a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ945652(v=OCS.15)
ms:contentKeyID: 52056441
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Hybriddomäne oder geteilte Domäne – AutoErmittlung

 

_**Letztes Änderungsdatum des Themas:** 2013-02-14_

Ein freigegebener SIP-Adressraum, auch als Bereitstellung mit *geteilter Domäne* oder *Hybridbereitstellung* bezeichnet, ist eine Konfiguration, bei der Benutzer in einer lokalen Bereitstellung und einer Onlineumgebung bereitgestellt werden. Das Ziel besteht darin, dass ein Benutzer sich unabhängig davon, wo sich sein Homeserver befindet (lokal oder online) bei der Bereitstellung anmeldet und an den Speicherort ihres Homeservers weitergeleitet wird. Dazu wird die AutoErmittlungsfunktion von Lync Server 2013 verwendet, um den Onlinebenutzer an die Onlinetopologie weiterzuleiten. Dazu konfigurieren Sie die AutoErmittlungs-URL mithilfe der Lync Server-Verwaltungsshell und der Cmdlets **Get-CsHostingProvider** und **Set-CsHostingProvider**.

## Mobilität für die Bereitstellung geteilter Domänen

Sie müssen folgende bereitgestellte Attribute erfassen und aufzeichnen:

  - Geben Sie in der Lync Server-Verwaltungsshell Folgendes ein:
    
        Get-CsHostingProvider

  - Suchen Sie in den Ergebnissen nach dem Onlineanbieter mit dem Attribut**ProxyFQDN**, z. B. "sipfed.online.lync.com".

  - Zeichnen Sie den Wert von "ProxyFQDN" auf.

  - Aktivieren Sie in der lokalen Lync Server-Systemsteuerung den Partnerverbund, und lassen so einen Partnerverbund mit dem Onlineanbieter zu.

  - Aktivieren Sie den Partnerverbund für den Onlineanbieter. Standardmäßig sind alle Onlinebenutzer für den Domänenverbund aktiviert und können mit allen Domänen kommunizieren.

  - Wenn Sie gesperrte und zulässige Domänen definieren, legen Sie die Domänen fest, die Sie explizit zulassen oder sperren möchten.

  - Für den Onlineverbund müssen Sie Firewallausnahmen, Zertifikate und den DNS-Hosteinträge (A oder AAAA bei Verwendung von IPv6) planen. Außerdem müssen Sie Verbundrichtlinien konfigurieren. Nähere Informationen finden Sie unter [Planen von Lync Server- und Office Communications Server-Partnerverbünden](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)

