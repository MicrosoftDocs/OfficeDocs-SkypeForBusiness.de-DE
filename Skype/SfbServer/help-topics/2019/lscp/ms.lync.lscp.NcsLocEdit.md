---
title: Standortrichtlinie zum Erstellen neuer oder Bearbeiten vorhandener Daten
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.NcsLocEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: d9b30b3b-570b-49a6-b2b4-46b0cf490153
ROBOTS: NOINDEX, NOFOLLOW
description: Sie können Standortrichtlinien konfigurieren, um zu bestimmen, ob E9-1-1 aktiviert ist, wie es verwendet wird und wie Standortinformationen für Benutzer und Kontakte verwendet werden.
ms.openlocfilehash: b4b67535c318e92ca951deaff167c0d86cc4d2a2
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41792193"
---
# <a name="location-policy-create-new-or-edit-existing"></a>Standortrichtlinie: Erstellen einer neuen oder Bearbeiten einer vorhandenen Standortrichtlinie

Sie können Standortrichtlinien konfigurieren, um zu bestimmen, ob E9-1-1 aktiviert ist, wie es verwendet wird und wie Standortinformationen für Benutzer und Kontakte verwendet werden.

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In der folgenden Liste werden die Felder der Seite beschrieben.

- **Bereich** Identifiziert den Bereich der Standortrichtlinie, die Sie erstellen oder ändern: Global, Site oder User.

- **Name** Für jede Standortrichtlinie ist ein Name erforderlich. Standortrichtlinien auf globaler Ebene und für Standorte erhalten standardmäßig einen Namen, der nicht geändert werden kann. Verwenden Sie für Standortrichtlinien einen beschreibenden Namen, mit dem der Benutzer oder die Benutzergruppe identifiziert wird.

    > [!NOTE]
    > Nachdem Sie die Standortrichtlinie gespeichert haben, kann der Name nicht mehr geändert werden.

- **Aktivieren von Enhanced 9-1-1 (E9-1-1)** Aktivieren Sie dieses Kontrollkästchen, um E9-1-1 für Benutzer zu aktivieren, denen diese Standortrichtlinie zugewiesen ist.

- **Ort** Angeben, ob Benutzer zur Angabe von Standortinformationen aufgefordert werden:

  - **Erforderlich** Wählen Sie diese Option aus, wenn Benutzer aufgefordert werden, Standortinformationen einzugeben, wenn sich der Client an einem neuen Speicherort registriert. Benutzer können die Eingabeaufforderung ohne Eingabe von Standortinformationen verwerfen.

  - **Nicht erforderlich** Wählen Sie diese Option aus, wenn Benutzer nicht zur Angabe von Standortinformationen aufgefordert werden sollen.

  - **Haftungsausschluss** Wählen Sie diese Option aus, wenn Benutzer zur Angabe von Standortinformationen aufgefordert werden sollen, aber eine Haftungsausschluss-Meldung angezeigt wird, wenn Sie die Eingabeaufforderung ablehnen, ohne die Informationen einzugeben. Benutzer können dann Notrufe tätigen, während für andere Anrufe zuerst die Eingabe von Standortinformationen erforderlich ist.

- **Verwenden Sie die Position nur für E9-1-1** Aktivieren Sie dieses Kontrollkästchen, wenn Standortinformationen nur für Notrufe verwendet werden sollen.

- **PSTN-Verwendung** Wählen Sie die PSTN-Nutzung (Public Switched Telephone Network) aus, die verwendet wird, um zu ermitteln, welche VoIP-Route für die Weiterleitung von Notrufen von Clients verwendet wird, die dieses Profil verwenden. Die dieser Verwendung zugeordnete Route muss auf einen SIP-Trunk verweisen, der speziell für Notrufe eingerichtet wurde, oder auf ein ELIN (Emergency Location Identification Number)-Gateway, das den Notruf an die nächstgelegene Rettungsleitstelle weiterleitet. Die Optionen lauten **Intern**, **Lokal** oder **Ferngespräche**.

- **E9-1-1-Wählnummer** Geben Sie die Nummer an, die gewählt wird, um Notfalldienste zu erreichen.

- **E9-1-1-Wähl Maske** Geben Sie eine Nummer an, die ein Benutzer wählt, die dann in die Notrufnummer übersetzt wird. Geben Sie in dieses Feld z. B. den Wert 212 ein, damit ein Benutzer 212 für die Notfalldienste wählen kann. Auf diese Weise können alternative Notrufnummern gewählt werden, und der Anruf kann immer noch in Notfällen erfolgen (Wenn beispielsweise jemand aus einem Land oder einer Region mit einer anderen Notrufnummer versucht, die Nummer des Landes oder der Region zu wählen, anstatt die Nummer des Land oder Region, in dem Sie sich gerade befinden). (Dies ist beispielsweise hilfreich, wenn jemand aus einem Land oder einer Region mit einer anderen Notrufnummer versucht, die Notrufnummer des eigenen Landes zu wählen, und nicht die Notrufnummer des Landes oder der Region, in dem/der er sich gerade aufhält.) Um mehrere Notrufmasken zu definieren, trennen Sie die Werte durch ein Semikolon, z. B. 212;414. Die maximale Länge der Zeichenfolge beträgt 100 Zeichen. Bei jedem Zeichen muss es sich um eine Ziffer von 0 bis 9 handeln.

    > [!IMPORTANT]
    > Stellen Sie sicher, dass die Wählmaske nicht mit einer Nummer im Nummernbereich zum Parken von Anrufen übereinstimmt, da die Weiterleitung zum Parken von Anrufen Vorrang vor der Konvertierung von Notrufwählzeichenfolgen hat. Klicken Sie in der linken Navigationsleiste auf **sprach Features** , und klicken Sie dann auf **Park anrufen**, um die Rufnummernbereiche des Anruf Parks anzuzeigen.

- **Benachrichtigungs-URI** Geben Sie einen oder mehrere SIP-URIs an, die bei einem Notfall Anruf benachrichtigt werden sollen. Geben Sie z. B. den SIP-URI der Sicherheitsstelle des Unternehmens ein, um das Sicherheitspersonal per Sofortnachricht zu benachrichtigen, wenn ein Notruf getätigt wird. Wenn der Standort des Anrufers verfügbar ist, ist der Standort in der Benachrichtigung enthalten. Sie können mehrere SIP-URIs als kommagetrennte Liste angeben. Beispiel: „sip:security@litwareinc.com“,„sip:kmyer@litwareinc.com“. Die Zeichenfolge muss zwischen 1 und 256 Zeichen lang sein und mit dem Präfix „sip:“ beginnen. Außerdem können Sie Verteilerlisten angeben.

- **Konferenz-URI** Geben Sie den SIP-URI (in diesem Fall die Telefonnummer) für eine Drittpartei an, die an Notrufen teilnimmt. Geben Sie z. B. die Telefonnummer der Sicherheitsstelle des Unternehmens ein, damit dort ein Anruf eingeht, wenn ein Notruf abgesetzt wird. Anhand der Einstellung unter **Konferenzmodus** wird festgelegt, ob der dritte Teilnehmer aktiv teilnehmen oder nur zuhören kann. Die Zeichenfolge muss zwischen 1 und 256 Zeichen lang sein und mit dem Präfix „sip:“ beginnen.

- **Konferenzmodus** Wenn Sie einen Wert für **Konferenz-URI**angegeben haben, setzen Sie dieses Feld auf einen der folgenden Werte:

  - **Unidirektional** Gibt an, dass der Drittanbieter nur den Anruf zwischen dem Anrufer und dem PSAP-Operator abhören kann.

  - **Bidirektional** Gibt an, dass der Drittanbieter am Anruf zwischen dem Anrufer und dem PSAP-Operator teilnehmen kann.

Ausführliche Informationen zu den Features und Funktionen des Enterprise-VoIP-Notfall Diensts finden Sie unter [Übersicht über E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) in der Planungsdokumentation. Ausführliche Informationen zur Verwendung von Standortrichtlinien finden Sie in der Betriebsdokumentation unter [Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx).


