---
title: Migrieren von analogen Geräten
TOCTitle: Migrieren von analogen Geräten
ms:assetid: ad072916-87ed-4d44-8289-aab87da86250
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ721846(v=OCS.15)
ms:contentKeyID: 49890885
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migrieren von analogen Geräten

 

_**Letztes Änderungsdatum des Themas:** 2012-10-16_

Lync Server bietet Unterstützung für analoge Geräte. Zu den unterstützten analogen Geräten gehören insbesondere analoge Telefone und Faxgeräte. Sie können die qualifizierten Gateways für die Unterstützung analoger Geräte in der Lync Server-Umgebung konfigurieren. Nach dem Migrieren von Lync Server 2010 zu Lync Server 2013 müssen Sie auch die Kontaktobjekte migrieren, die den analogen Geräten zugeordnet sind. Rufen Sie zunächst mit der Lync Server-Verwaltungsshell alle Kontaktobjekte ab, die den analogen Lync Server 2010-Geräten zugeordnet sind, und verschieben Sie diese Objekte anschließend in den Lync Server 2013-Pool.

## So migrieren Sie analoge Geräte

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Geben Sie an der Befehlszeile Folgendes ein:
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net

3.  Stellen Sie sicher, dass alle Kontaktobjekte in den Lync Server 2013-Pool verschoben wurden. Geben Sie an der Befehlszeile Folgendes ein:
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}

4.  Stellen Sie sicher, dass nun alle Kontaktobjekte dem Lync Server 2013-Pool zugeordnet sind.

