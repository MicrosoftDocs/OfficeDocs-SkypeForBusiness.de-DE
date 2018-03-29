---
title: Ortungsrichtlinie Erstellen einer neuen oder Bearbeiten einer vorhandenen
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.NcsLocEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9b30b3b-570b-49a6-b2b4-46b0cf490153
description: Sie können Standortrichtlinien konfigurieren, um zu bestimmen, ob E9-1-1 aktiviert ist, wie es verwendet wird und wie Standortinformationen für Benutzer und Kontakte verwendet werden.
ms.openlocfilehash: cc2d5119e4bb21badf96dcf24099844ffffd0639
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="location-policy-create-new-or-edit-existing"></a>Standortrichtlinie: Erstellen einer neuen oder Bearbeiten einer vorhandenen Standortrichtlinie
 
Sie können Standortrichtlinien konfigurieren, um zu bestimmen, ob E9-1-1 aktiviert ist, wie es verwendet wird und wie Standortinformationen für Benutzer und Kontakte verwendet werden.
  
## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In der folgenden Liste werden die Felder der Seite beschrieben.
  
- **Bereich** Gibt den Bereich der Standortrichtlinie an, die Sie erstellen oder ändern: global, Standort oder Benutzer.
    
- **Name** Jede ortungsrichtlinie erfordert einen Namen an. Standortrichtlinien auf globaler Ebene und für Standorte erhalten standardmäßig einen Namen, der nicht geändert werden kann. Verwenden Sie für Standortrichtlinien einen beschreibenden Namen, mit dem der Benutzer oder die Benutzergruppe identifiziert wird.
    
    > [!NOTE]
    > Nachdem Sie die Standortrichtlinie gespeichert haben, kann der Name nicht mehr geändert werden. 
  
- **Aktivieren von erweiterten E9-1-1 (E9-1-1)** Aktivieren Sie dieses Kontrollkästchen, um E9-1-1 für Benutzer zu aktivieren, die dieser Standortrichtlinie zugewiesen sind.
    
- **Speicherort** Geben Sie an, ob Benutzer Standortinformationen aufgefordert werden:
    
  - **Erforderlich** Wählen Sie diese Option aus, wenn Benutzer Standortinformationen aufgefordert, wenn deren Clients an einem neuen Standort registriert sind. Benutzer können die Eingabeaufforderung ohne Eingabe von Standortinformationen verwerfen.
    
  - **Nicht erforderlich** Wählen Sie diese Option aus, wenn Benutzer nicht Standortinformationen aufgefordert werden.
    
  - **Haftungsausschluss** Wählen Sie diese Option aus, wenn Benutzer Standortinformationen aufgefordert werden, aber eine Nachricht Haftungsausschluss angezeigt werden, wenn sie die Aufforderung ablehnen, ohne die Informationen einzugeben. Benutzer können dann Notrufe tätigen, während für andere Anrufe zuerst die Eingabe von Standortinformationen erforderlich ist.
    
- **Verwenden des Speicherorts für E9-1-1 nur** Aktivieren Sie dieses Kontrollkästchen, wenn Standortinformationen nur für Notrufe verwendet werden.
    
- **PSTN-Verwendung** Wählen Sie das Telefonfestnetz (PSTN) Netzwerkauslastung, das verwendet wird, um zu bestimmen, welche VoIP-Route für die Weiterleitung von Notrufen von Clients verwendet werden soll, die dieses Profil verwenden. Die dieser Verwendung zugeordnete Route muss auf einen SIP-Trunk verweisen, der speziell für Notrufe eingerichtet wurde, oder auf ein ELIN (Emergency Location Identification Number)-Gateway, das den Notruf an die nächstgelegene Rettungsleitstelle weiterleitet. Die Optionen lauten **Intern**, **Lokal** oder **Ferngespräche**.
    
- **E9-1-1-Nummer** Geben Sie die Nummer, die zum Erreichen der notrufdienste gewählt wird.
    
- **Wählen Sie eine E9-1-1 Maske** Geben Sie eine Zahl, die ein Benutzer wählt, die dann in die Notrufnummer Nummer übersetzt wird. Geben Sie in dieses Feld z. B. den Wert 212 ein, damit ein Benutzer 212 für die Notfalldienste wählen kann. Dies ermöglicht eine alternative Notfall Nummern in gewählt werden und immer noch den Anruf erreichen der notrufdienste (z. B., wenn eine Person aus einem Land oder einer Region mit einem anderen Notrufnummer versucht, einwählen, Land oder Region Nummern und nicht die Anzahl für's der Land oder Region, die sie gerade werden). (Dies ist beispielsweise hilfreich, wenn jemand aus einem Land oder einer Region mit einer anderen Notrufnummer versucht, die Notrufnummer des eigenen Landes zu wählen, und nicht die Notrufnummer des Landes oder der Region, in dem/der er sich gerade aufhält.) Um mehrere Notrufmasken zu definieren, trennen Sie die Werte durch ein Semikolon, z. B. 212;414. Die maximale Länge der Zeichenfolge beträgt 100 Zeichen. Bei jedem Zeichen muss es sich um eine Ziffer von 0 bis 9 handeln.
    
    > [!IMPORTANT]
    > Stellen Sie sicher, dass die Wählmaske nicht mit einer Nummer im Nummernbereich zum Parken von Anrufen übereinstimmt, da die Weiterleitung zum Parken von Anrufen Vorrang vor der Konvertierung von Notrufwählzeichenfolgen hat. Um die Parken Bereiche angezeigt wird, klicken Sie in der linken Navigationsleiste auf **VoIP-Funktionen** , und klicken Sie dann auf **Anruf Parken**. 
  
- **Benachrichtigungs-URI** Geben Sie einen oder mehrere SIP-URIs benachrichtigt werden, wenn ein Notruf vorgenommen wird. Geben Sie z. B. den SIP-URI der Sicherheitsstelle des Unternehmens ein, um das Sicherheitspersonal per Sofortnachricht zu benachrichtigen, wenn ein Notruf getätigt wird. Wenn dem Standort des Anrufers verfügbar ist, ist der Speicherort in der Benachrichtigung enthalten. Sie können mehrere SIP-URIs als kommagetrennte Liste angeben. Beispiel: „sip:security@litwareinc.com“,„sip:kmyer@litwareinc.com“. Die Zeichenfolge muss zwischen 1 und 256 Zeichen lang sein und mit dem Präfix „sip:“ beginnen. Außerdem können Sie Verteilerlisten angeben.
    
- **Konferenz-URI** Geben Sie den SIP-URI (in diesem Fall Telefonnummer) für ein Drittanbieter per Konferenz zugeschaltet auf Notrufe sein. Geben Sie z. B. die Telefonnummer der Sicherheitsstelle des Unternehmens ein, damit dort ein Anruf eingeht, wenn ein Notruf abgesetzt wird. Anhand der Einstellung unter **Konferenzmodus** wird festgelegt, ob der dritte Teilnehmer aktiv teilnehmen oder nur zuhören kann. Die Zeichenfolge muss zwischen 1 und 256 Zeichen lang sein und mit dem Präfix „sip:“ beginnen.
    
- **Konferenzmodus** Wenn Sie einen Wert für **Konferenz-URI**angegeben haben, legen Sie dieses Feld auf einen der folgenden Werte:
    
  - **Unidirektionale** Gibt an, dass der dritte Teilnehmer dem Gespräch zwischen dem Anrufer und der rettungsleitstelle nur zuhören kann.
    
  - **Bidirektionale** Gibt an, dass der dritte Teilnehmer die Unterhaltung zwischen dem Anrufer und der rettungsleitstelle teilnehmen können.
    
Weitere Informationen zu Enterprise-VoIP notrufunterstützung Features und Funktionen finden Sie unter [Übersicht über E9-1-1](http://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) in der Planungsdokumentation. Ausführliche Informationen zum Arbeiten mit ortungsrichtlinien finden Sie unter [Standortrichtlinie konfigurieren](http://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) in der Betriebsdokumentation.
  

