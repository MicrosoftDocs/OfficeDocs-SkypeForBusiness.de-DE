---
title: 'Lync Server 2013: Remoteanrufsteuerung und Normalisieren von Rufnummern'
TOCTitle: Remoteanrufsteuerung und Normalisieren von Rufnummern
ms:assetid: 291d9e87-4c65-4ea2-888f-517741391de5
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg558630(v=OCS.15)
ms:contentKeyID: 49293495
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remoteanrufsteuerung und Normalisieren von Rufnummern in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-22_

Lync-Clients laden Normalisierungsregeln für Rufnummern im Rahmen des Adressbuchdienst-Dateidownloads herunter. In Szenarien mit Remoteanrufsteuerung werden die vom Adressbuchdienst verwendeten Normalisierungsregeln für Rufnummern sowohl auf eingehende als auch auf ausgehende Anrufe mit Remoteanrufsteuerung angewendet. Für eingehende Anrufe bei einem Benutzer, der für die Remoteanrufsteuerung aktiviert ist, wird die Rufnummer des Anrufers zunächst über das SIP/CSTA-Gateway oder eine Nebenstellenanlage (Private Branch Exchange, PBX) in das E.164-Format normalisiert. Wenn Lync Server 2013 einen Anruf vom Gateway empfängt, wird für die Rufnummer des Anrufers eine umgekehrte Nummernsuche nach der normalisierten Nummer in der Microsoft Office Outlook-Kontaktliste oder der globalen Adressliste des Anrufempfängers durchgeführt, die im Adressbuchdienst gespeichert sind. Wenn die umgekehrte Nummernsuche zu einem Treffer führt, wird der Anrufer in der Benachrichtigung über einen eingehenden Anruf mit seinem Namen identifiziert.

Für ausgehende Anrufe mit Remoteanrufsteuerung wendet Lync die vom Adressbuchdienst verwendeten Normalisierungsregeln für Rufnummern auf die gewählte Nummer an, bevor der Anruf an das SIP/CSTA-Gateway geroutet wird.

Ausführliche Informationen zum Erstellen von Normalisierungsregeln für Rufnummern bei Verwendung der Remoteanrufsteuerung finden Sie unter [Wählpläne und Normalisierungsregeln in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in der Planungsdokumentation.

## Migrieren von Normalisierungsregeln für Rufnummern

Wenn Sie Benutzer migrieren, die zuvor für die Remoteanrufsteuerung aktiviert waren, finden Sie weitere Informationen in den folgenden Themen der Migrationsdokumentation:

  - Informationen zur Vorgehensweise für Lync Server 2010 finden Sie unter [Migrieren des Adressbuchs](migrate-address-book.md) in der Migrationsdokumentation.

  - Informationen zur Vorgehensweise für Communications Server 2007 R2 finden Sie unter [Migrieren eines Adressbuchs](migrate-address-book_1.md) in der Migrationsdokumentation.

