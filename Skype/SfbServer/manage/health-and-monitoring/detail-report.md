---
title: Detaillierter Konferenzbericht in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
description: 'Zusammenfassung: Erfahren Sie mehr über den in Skype for Business Server verwendeten Konferenzdetailbericht.'
ms.openlocfilehash: a86124c05e0d35caef3f92c4ec43b561eb54938c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60829989"
---
# <a name="conference-detail-report-in-skype-for-business-server"></a>Detaillierter Konferenzbericht in Skype for Business Server

**Zusammenfassung:** Erfahren Sie mehr über den in Skype for Business Server verwendeten Konferenzdetailbericht.

Der detaillierte Konferenzbericht enthält ausführliche Informationen zu allen Benutzern, die an einer Konferenz teilgenommen haben. Sie können beispielsweise Informationen wie Datum und Uhrzeit, an dem bzw. zu der ein Benutzer einer Konferenz beigetreten ist und die Konferenz verlassen hat, sowie den Benutzer-Agent des Endpunkts anzeigen, mit dem der Benutzer mit der Konferenz verbunden wurde. Darüber hinaus können Sie Informationen zu der Rolle des Benutzers in den einzelnen Konferenzen (z. B. Referent oder Teilnehmer) anzeigen. Der vielleicht wichtigste Aspekt ist, dass Sie auf einen Blick erkennen können, welche Benutzer der Konferenz erfolgreich beigetreten und sie abgeschlossen haben und welche Benutzer der Konferenz nicht beitreten konnten und sie daher nicht abgeschlossen haben.

## <a name="accessing-the-conference-detail-report"></a>Zugreifen auf den detaillierten Konferenzbericht

Auf den detaillierten Konferenzbericht kann über die folgenden Berichte zugegriffen werden:

- [Call Admission Control Report](call-admission-control-report.md) (durch Klicken auf die Metrik "Detail" für eine Konferenz)

- [Failure List Report](failure-list-report.md) (durch Klicken auf die Metrik "Konferenz")

- [User Activity Report](call-diagnostic-reports-per-user.md) (durch Klicken auf die Metrik "Konferenz-URI")

Über den detaillierten Konferenzbericht können Sie auf den [Diagnostic Report](diagnostic-report.md) zugreifen, indem Sie auf die Metrik für den Diagnosebericht (Detail) klicken.

## <a name="filters"></a>Filter

Keine. Der detaillierte Konferenzbericht lässt sich nicht filtern.

## <a name="metrics"></a>Metriken

In der folgenden Tabelle werden die Informationen aus dem Abschnitt zu Konferenzinformationen des detaillierten Konferenzberichts aufgeführt.

**Konferenzinformationen – Metriken**


| **Name**                 | **Beschreibung**                                                                                                            |
|:-------------------------|:---------------------------------------------------------------------------------------------------------------------------|
| **Konferenz-URI** <br/> | Der Konferenz zugewiesener URI. Beispiel:  <br/> sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4  <br/> |
| **Pool-FQDN** <br/>      | Vollqualifizierter Domänenname des Registrierungspools oder Edgeservers in einer Sitzung.  <br/>                             |
| **Beginn** <br/>     | Datum und Uhrzeit, an dem bzw. zu der Konferenz begann.  <br/>                                                                          |
| **Organisator** <br/>      | SIP-Adresse des Benutzers, der die Sitzung organisiert hat.  <br/>                                                               |
| **Endzeit** <br/>       | Datum und Uhrzeit, an dem bzw. zu der die Konferenz endete.  <br/>                                                                            |

In der folgenden Tabelle werden die Informationen aus dem Abschnitt zur Konferenzteilnahme des detaillierten Konferenzberichts aufgeführt.

**Konferenzteilnahme – Metriken**

|**Name**|**Beschreibung**|
|:-----|:-----|
|**Benutzer** <br/> |SIP-Adresse des Benutzers, der an der Konferenz teilgenommen hat.  <br/> |
|**Rolle** <br/> |Rolle (z. B. Referent) des Konferenzteilnehmers.  <br/> |
|**Verbindung** <br/> |Netzwerkverbindungen (in der Regel "From Internal" oder "From External") des Teilnehmers.  <br/> |
|**Zeitpunkt des Beitritts** <br/> |Datum und Uhrzeit, an dem bzw. zu der der Teilnehmer der Konferenz beigetreten ist.  <br/> |
|**Zeitpunkt der Beendigung** <br/> |Datum und Uhrzeit, an dem bzw. zu der der Teilnehmer die Konferenz verlassen hat.  <br/> |
|**Benutzer-Agent** <br/> |Bezeichner für die vom Endpunkt des Teilnehmers verwendete Software.  <br/> |
|**Diagnoseberichte** <br/> |Enthält Diagnose- und Problembehandlungsinformationen, einschließlich SIP-Antwortcodes, Diagnoseheader, Zeitpunkt des Konferenzbeitritts und Diagnose-IDs für fehlgeschlagene Sitzungen.  <br/> |

In der folgenden Tabelle sind die Informationen aufgeführt, die im Abschnitt "Konferenzmodalitäten" des Detaillierten Konferenzberichts enthalten sind.

**Konferenzmodalitäten – Metriken**

|**Name**|**Beschreibung**|
|:-----|:-----|
|**Benutzer** <br/> |SIP-Adresse des Benutzers, der an der Konferenz teilgenommen hat.  <br/> |
|**Zeitpunkt des Beitritts** <br/> |Datum und Uhrzeit, an dem bzw. zu der der Teilnehmer der Konferenz beigetreten ist.  <br/> |
|**Zeitpunkt der Beendigung** <br/> |Datum und Uhrzeit, an dem bzw. zu der ein Teilnehmer die Konferenz verlassen hat.  <br/> |
|**Konferenzserver-URI** <br/> |URI für den in der Konferenz verwendeten Konferenzserver.  <br/> |
|**Diagnoseberichte** <br/> |Enthält Diagnose- und Problembehandlungsinformationen, einschließlich SIP-Antwortcodes, Diagnoseheader, Zeitpunkt des Konferenzbeitritts und Diagnose-IDs für fehlgeschlagene Sitzungen.  <br/> |


