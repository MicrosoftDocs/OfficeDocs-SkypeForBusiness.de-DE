---
title: Standortrichtlinie Erstellen einer neuen oder Bearbeiten einer vorhandenen Standortrichtlinie
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.NcsLocEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9b30b3b-570b-49a6-b2b4-46b0cf490153
description: Sie können Standortrichtlinien konfigurieren, um zu bestimmen, ob 9-1-1 (E9-1-1) aktiviert ist und wie sie verwendet werden und wie Standortinformationen für Benutzer und Kontakte verwendet werden.
ms.openlocfilehash: f171d841ec68b3e0b0b4f7c8b9d374ff2261d149
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803965"
---
# <a name="location-policy-create-new-or-edit-existing"></a>Ortungsrichtlinie: Erstellen einer neuen oder Bearbeiten einer vorhandenen Ortungsrichtlinie

Sie können Standortrichtlinien konfigurieren, um zu bestimmen, ob 9-1-1 (E9-1-1) aktiviert ist und wie sie verwendet werden und wie Standortinformationen für Benutzer und Kontakte verwendet werden.

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In der folgenden Liste sind die Felder der Seite beschrieben.

- **Bereich** Gibt den Bereich der Standortrichtlinie an, die Sie erstellen oder ändern: global, Standort oder Benutzer.

- **Name** Jede Standortrichtlinie erfordert einen Namen. Standortrichtlinien auf globaler Ebene und für Standorte erhalten standardmäßig einen Namen, der nicht geändert werden kann. Verwenden Sie für Standortrichtlinien einen beschreibenden Namen, mit dem der Benutzer oder die Benutzergruppe identifiziert wird.

    > [!NOTE]
    > Nachdem Sie die Standortrichtlinie gespeichert haben, kann der Name nicht mehr geändert werden.

- **Aktivieren der erweiterten 9-1-1-Funktion (E9-1-1)** Aktivieren Sie dieses Kontrollkästchen, um E9-1-1 für Benutzer zu aktivieren, denen diese Standortrichtlinie zugewiesen ist.

- **Position** Geben Sie an, ob Benutzer zur Eingabe von Standortinformationen aufgefordert werden:

  - **Erforderlich** Wählen Sie diese Option aus, wenn Benutzer zur Eingabe von Standortinformationen aufgefordert werden sollen, wenn sich ihr Client an einem neuen Standort registriert. Benutzer können die Eingabeaufforderung ohne Eingabe von Standortinformationen verwerfen.

  - **Nicht erforderlich** Wählen Sie diese Option aus, wenn Benutzer nicht zur Eingabe von Standortinformationen aufgefordert werden sollen.

  - **Haftungsausschluss** Wählen Sie diese Option aus, wenn Benutzer zur Eingabe von Standortinformationen aufgefordert werden sollen, jedoch eine Haftungsausschlussmeldung angezeigt wird, wenn sie die Eingabeaufforderung ablehnen, ohne die Informationen ein eingeben zu müssen. Benutzer können dann Notrufe tätigen, während für andere Anrufe zuerst die Eingabe von Standortinformationen erforderlich ist.

- **Standort nur für E9-1-1 verwenden** Aktivieren Sie dieses Kontrollkästchen, wenn Standortinformationen nur für Notrufe verwendet werden sollen.

- **PstN-Verwendung** Wählen Sie die Verwendung des Telefonnetzes (Public Switched Telephone Network, PSTN) aus, die verwendet wird, um zu bestimmen, welche Sprachroute zum Weiterleiten von Notrufen von Clients verwendet wird, die dieses Profil verwenden. Die dieser Verwendung zugeordnete Route muss auf einen SIP-Trunk verweisen, der speziell für Notrufe eingerichtet wurde, oder auf ein ELIN (Emergency Location Identification Number)-Gateway, das den Notruf an die nächstgelegene Rettungsleitstelle weiterleitet. Die Optionen lauten **Intern**, **Lokal** oder **Ferngespräche**.

- **E9-1-1-Wählnummer** Geben Sie die Nummer an, die zum Erreichen der Notrufdienste gewählt wird.

- **E9-1-1-Wählmaske** Geben Sie eine Nummer an, die ein Benutzer wählt, die dann in die Notrufnummer übersetzt wird. Geben Sie in dieses Feld z. B. den Wert 212 ein, damit Benutzer 212 für die Notfalldienste wählen kann. Auf diese Weise können alternative Notrufnummern gewählt werden, und der Anruf wird weiterhin an die Notrufdienste angerufen (z. B. wenn jemand aus einem Land oder einer Region mit einer anderen Notrufnummer versucht, die Nummer dieses Landes oder dieser Region anstelle der Nummer für das Land oder die Region zu wählen, in dem sie sich derzeit befinden). (Dies ist beispielsweise hilfreich, wenn jemand aus einem Land oder einer Region mit einer anderen Notrufnummer versucht, die Notrufnummer des eigenen Lands zu wählen, und nicht die Notrufnummer des Lands oder der Region, in dem/der er sich gerade aufhält.) Um mehrere Notrufmasken zu definieren, trennen Sie die Werte durch ein Semikolon, z. B. 212;414. Die maximale Länge der Zeichenfolge beträgt 100 Zeichen. Bei jedem Zeichen muss es sich um eine Ziffer von 0 bis 9 handeln.

    > [!IMPORTANT]
    > Stellen Sie sicher, dass die Wählmaske nicht mit einer Nummer im Nummernbereich zum Parken von Anrufen übereinstimmt, da die Weiterleitung zum Parken von Anrufen Vorrang vor der Konvertierung von Notrufwählzeichenfolgen hat. Klicken Sie in der linken Navigationsleiste auf **"Sprachfunktionen",** und klicken Sie dann auf "Anruf parken", um die Nummernbereiche für das Parken von Anrufen **zu sehen.**

- **Benachrichtigungs-URI** Geben Sie eine oder mehrere SIP-URIs an, die bei einem Notruf benachrichtigt werden sollen. Geben Sie z. B. den SIP-URI der Sicherheitsstelle des Unternehmens ein, um das Sicherheitspersonal per Sofortnachricht zu benachrichtigen, wenn ein Notruf getätigt wird. Wenn der Standort des Anrufers verfügbar ist, ist der Standort in der Benachrichtigung enthalten. Sie können mehrere SIP-URIs als kommagetrennte Liste angeben. Beispiel: "sip:security@litwareinc.com","sip:kmyer@litwareinc.com". Die Zeichenfolge muss zwischen 1 und 256 Zeichen lang sein und mit dem Präfix "sip:" beginnen. Außerdem können Sie Verteilerlisten angeben.

- **Konferenz-URI** Geben Sie den SIP-URI (in diesem Fall Telefonnummer) für einen Drittanbieter an, der in Notrufe eingerufen werden soll. Geben Sie z. B. die Telefonnummer der Sicherheitsstelle des Unternehmens ein, damit dort ein Anruf eingeht, wenn ein Notruf abgesetzt wird. Anhand der Einstellung unter **Konferenzmodus** wird festgelegt, ob der dritte Teilnehmer aktiv teilnehmen oder nur zuhören kann. Die Zeichenfolge muss zwischen 1 und 256 Zeichen lang sein und mit dem Präfix "sip:" beginnen.

- **Konferenzmodus** Wenn Sie einen Wert für den **Konferenz-URI** angegeben haben, legen Sie dieses Feld auf einen der folgenden Werte fest:

  - **One-way** Gibt an, dass der Dritte nur den Anruf zwischen dem Anrufer und der PsAP-Operator abhören kann.

  - **Zwei-Wege-Methode** Gibt an, dass der Dritte am Anruf zwischen dem Anrufer und der Anbieterin für die Telefonfestnetzanrufe teilnehmen kann.

Ausführliche Informationen zu Enterprise-VoIP und -funktionen finden Sie in der Übersicht über [E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) in der Planungsdokumentation. Ausführliche Informationen zur Verwendung von Standortrichtlinien finden Sie unter [Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) in der Betriebsdokumentation.


