---
title: Überprüfen des Zertifikatberichts in Lync Server 2013
TOCTitle: Überprüfen des Zertifikatberichts in Lync Server 2013
ms:assetid: 549cfc9b-3cc5-4483-a93c-fc0738c7f622
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg558651(v=OCS.15)
ms:contentKeyID: 52056363
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Überprüfen des Zertifikatberichts in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Der Zertifikatbericht enthält sämtliche Zertifikate, die in der empfohlenen Lync Server 2013-Bereitstellung benötigt werden. Das Planungstool erfasst die eingegebenen Antragstellernamen und alternativen Antragstellernamen. Nicht bearbeiteter Standardtext kann eine Herausforderung für das Team darstellen, das für das Anfordern und Ausstellen der Zertifikate verantwortlich ist. In den Zertifikatinformationen ist zudem angegeben, von welcher Stelle das Zertifikat typischerweise ausgestellt werden kann. Wenn die Infrastruktur nicht über eine interne Public Key-Infrastruktur (PKI) verfügt, können sämtliche Zertifikate über einen öffentlichen Zertifikatanbieter angefordert werden. Die Felder "Erweiterte Schlüsselverwendungen" und "Zuweisen zu" des Berichts sind äußerst nützlich und liefern Informationen zum Zweck und Speicherort der einzelnen Zertifikate.

![Zertifikatverwaltungsbericht](images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "Zertifikatverwaltungsbericht")

Prüfen Sie die Verwendung und den Zweck der einzelnen Zertifikate innerhalb der Bereitstellung sorgfältig, und stellen Sie sicher, dass sie diese Informationen verstanden haben. Wenn Sie Fragen zum Zweck eines Zertifikats haben, ermitteln Sie, welcher Server oder Dienst mit welcher Komponente kommuniziert. In Lync Server 2013 werden Zertifikate in erster Linie für zwei Zwecke eingesetzt:

  - Mutual Transport Layer Security (MTLS) – Die Computer, die miteinander kommunizieren, belegen ihre Identität gegenüber den anderen Computern mithilfe eines Zertifikats. Dieser Vorgang wird als Serverauthentifizierung bezeichnet. Die Kommunikation ist erst möglich, wenn sämtliche Computer die Identität der anderen Computer als vertrauenswürdig eingestuft haben.

  - Verschlüsselung – Die Verschlüsselung (Secure Sockets Layer, SSL, und Transport Layer Security, TLS) ist eine wichtige Methode, um eine sichere Kommunikation und die Einhaltung von Datenschutzrichtlinien zu gewährleisten sowie ein vertrauenswürdiges System für Kommunikation und Zusammenarbeit zu erstellen.

## Siehe auch

#### Weitere Ressourcen

[Überprüfen der Administratorberichte in Lync Server 2013](lync-server-2013-reviewing-the-administrator-reports.md)

