---
title: ProgressReport-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
description: Statusberichte basieren auf Daten, die vom Client nach Abschluss eines Anrufs oder einer Sitzung an die Datenbank hochgeladen wurden. Fortschrittsberichte werden nur für Anrufe und Sitzungen geschrieben, die von Skype for Business Server 2015 für diagnostische Zwecke nützlich sein können.
ms.openlocfilehash: 9022c7707e0d2f0a4346ed629bf51420c312b10a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295902"
---
# <a name="progressreport-table"></a>ProgressReport-Tabelle
 
Statusberichte basieren auf Daten, die vom Client nach Abschluss eines Anrufs oder einer Sitzung an die Datenbank hochgeladen wurden. Fortschrittsberichte werden nur für Anrufe und Sitzungen geschrieben, die von Skype for Business Server 2015 für diagnostische Zwecke nützlich sein können.
  
Die Felder "Fehler", "ErrorReportSeq" und "ProgressReportSeq" beziehen sich nicht unbedingt auf Fehler, sondern auf Nachrichten, die den Status von anrufen oder Nachrichten angeben.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**Fehlerzeit** <br/> |datetime  <br/> |Primär, fremd  <br/> |Datum und Uhrzeit des Status Fehlerberichts, der diesen Statusbericht enthält. Weitere Informationen finden Sie [in der Tabelle errorreport in Skype for Business Server 2015](errorreport.md) . <br/> |
|**ErrorID** <br/> |int  <br/> |Primär, fremd  <br/> |ID-Nummer, die in Verbindung mit Fehlerzeit verwendet wird, ProgressReportSeq, um einen Statusbericht eindeutig zu identifizieren. Weitere Informationen finden Sie [in der Tabelle errorreport in Skype for Business Server 2015](errorreport.md) . <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Primär, fremd  <br/> |Die ID-Nummer, die den Fehlerbericht identifiziert. ErrorReporSeq wird in Verbindung mit Fehlerzeit verwendet, um einen Fehlerbericht eindeutig zu identifizieren. Weitere Informationen finden Sie [in der Tabelle errorreport in Skype for Business Server 2015](errorreport.md) . <br/> Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**ProgressReportSeq** <br/> |int  <br/> |Primary  <br/> |Die ID-Nummer zur Identifizierung des Statusberichts. Wird in Verbindung mit Fehlerzeit und ErrorReportSeq verwendet, um einen Statusbericht eindeutig zu identifizieren.  <br/> |
|**MsDiagId** <br/> |int  <br/> ||Diagnose-ID des Statusberichts  <br/> Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**SourceID** <br/> |int  <br/> |Fremd  <br/> |Der Server, der den Fehlerbericht gesendet hat (wenn der Bericht von einer Serverkomponente gesendet wurde). Weitere Informationen finden Sie in der [Tabelle Server](servers.md) . Dieses Feld wurde in Microsoft lync Server 2013 eingeführt. <br/> |
|**ApplicationId** <br/> |int  <br/> ||Der lync-Server Prozess, zu dem der Bericht gehört. Weitere Informationen finden Sie in der Anwendungstabelle.  <br/> |
|**Detail** <br/> |Bild  <br/> ||Details des Statusberichts, die im Binärformat gespeichert werden, um Platz zu sparen. Diese Daten können mit dieser Syntax in das Text Format konvertiert werden:  <br/> Umwandlung (Umwandlung (Detail als varbinary (max)) als varchar (max))  <br/> |
|**Telemetrie** <br/> |uniqueIdentifier  <br/> ||Eindeutiger Bezeichner, der die Verknüpfungszeit Informationen für die verschiedenen an einer Konferenz beteiligten Komponenten korreliert.  <br/> Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> ||Zeit (in Millisekunden) für eine bestimmte Komponente, um an einer Konferenz teilzunehmen.  <br/> Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
   

