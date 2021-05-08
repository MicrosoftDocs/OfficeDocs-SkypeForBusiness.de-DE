---
title: Einrichten der gemeinsamen Telefon-Lizenz
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 12/13/2018
ms.reviewer: kponnus
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: 'Erfahren Sie, wie Sie Telefone im allgemeinen Bereich für Lobbys, Empfangsbereiche und Konferenzräume einrichten. '
ms.openlocfilehash: bb17b21eac262c160abc3e16a4b552fb32b97d00
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117113"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a>Einrichten der Lizenz für Telefone für gemeinsame Bereiche für Microsoft Teams
> [!NOTE]
> Häufige Telefone in der Nähe unterstützen keine Voicemail.

Ein Telefon in der Nähe eines Telefons befindet sich normalerweise in einem Bereich wie einem Wartebereich oder einem anderen Bereich, der von vielen Personen für einen Anruf verwendet werden kann. z. B. einen Empfangsbereich, einen Wartebereich oder ein Konferenztelefon. Telefone in gängigen Gegenden sind mit Konten angemeldet, die an eine gemeinsame Telefon gebunden sind. Die TeamsIPPhone-Richtlinie muss auch entsprechend festgelegt sein, damit das Telefon in einem gemeinsamen Bereich benutzerfreundliche Benutzerfreundlichkeit hat.

In den nachstehenden Schritten helfen wir Ihnen beim Einrichten eines Kontos für Telefonsystem Bereitstellung von Telefonen in der Nähe für Ihre Organisation. Für eine vollständigere Besprechungsraumerfahrung, einschließlich Audiokonferenzen, sollten Sie die dedizierte Lizenz Besprechungsraum einem Besprechungsraumgerät erwerben. 

Zuerst müssen Sie eine Cap-Lizenz (Common Area Telefon) erwerben und sicherstellen, dass Sie über ein zertifiziertes Telefon verfügen. Weitere Informationen zu zertifizierten Telefonen finden Sie unter [Microsoft Teams-Geräte.](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1) 

## <a name="step-1---buy-the-licenses"></a>Schritt 1 - Lizenzen kaufen

1. Wechseln Sie Microsoft 365 Admin Center zu **Dienste für** Abrechnungskäufe, und erweitern Sie dann Andere  >   **Pläne**.

    ![Screenshot der Kachel "Gemeinsame Telefon"](media/set-up-common-area-phone-image1.png)

2. Wählen **Sie Gemeinsamen Bereich Telefon** Jetzt kaufen  >  **aus.**

3. Klicken Sie auf der Seite Auschecken **auf Jetzt kaufen**.

4. Erweitern **Sie Add-On-Abonnements,** und klicken Sie dann auf , um einen Anrufplan zu kaufen. Wählen Sie entweder den **Plan für Inlandsrufe** oder **einen Plan für Inlands- und Auslandsrufe aus.**

> [!NOTE]
> Wenn Sie ihr System Direct Microsoft-Telefon Routing verwenden, benötigen Sie keine Lizenz für einen Anrufplan.

> [!NOTE]
> Sie müssen keine Lizenz Telefonsystem hinzufügen. Sie ist in der Lizenz Telefon für gemeinsame Bereiche enthalten.

Weitere Informationen zu Lizenzen finden Sie unter [Microsoft Teams Add-On-Lizenzierung.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

Der gemeinsame Bereich, Telefon von der Lizenz unterstützt wird: 


|   |  Telefon für gemeinsame Bereiche  |
|---------|---------|
|Skype for Business |   &#x2714; |
|Microsoft Teams |   &#x2714; |
|Telefonsystem |    &#x2714; |
|Audiokonferenzen |       &#x2718; &Sup1;  |
|Microsoft Intune |    &#x2718; |
|Weltweite Verfügbarkeit |       &#x2718; &Sup2;  |
|Verfügbarkeit von Kanälen |    EA, EAS, CSP, GCC, EES, Web Direct  |
|      |         |

&Sup1; Telefone vor Ort können über die vom Besprechungsorganisator bereitgestellte Einwahlnummer an Audiokonferenzen teilnehmen.

&Sup2; In souveränen Wolken nicht verfügbar  



## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>Schritt 2 - Ein neues Benutzerkonto für das Telefon erstellen und die Lizenzen zuweisen

1. Wechseln Sie Microsoft 365 Admin Center zu Benutzer, die  >  **aktive Benutzer**  >  **hinzufügen.**

2. Geben Sie einen Benutzernamen wie "Main" für den Vornamen und "Empfang" für den zweiten Namen ein.

3. Geben Sie einen Anzeigenamen ein, wenn dieser nicht automatisch generiert wird, z. B. "Hauptaufnahme".

4. Geben Sie einen Benutzernamen wie "Main Umleitung" oder "Mainlobby" ein.

5. Bei Telefonen in gängigen Telefonen in der Nähe können Sie ein Kennwort manuell festlegen oder für alle Telefone in der Nähe des gleichen Kennworts verwenden. Darüber hinaus können Sie auch das Kontrollkästchen Diesen Benutzer bei der ersten Anmeldung an das Kennwort **ändern** lassen aktivieren.

6. Weisen Sie die Lizenzen dem Benutzer zu. Klicken Sie auf der gleichen Seite auf **Produktlizenzen** erweitern. Aktivieren Sie das gemeinsame Telefon und wählen  Sie entweder einen Plan für Inlandsrufe oder einen Plan für **Inlands- und Auslandsrufe aus.** 

    ![Screenshot mit Lizenzzuweisung](media/set-up-common-area-phone-image2.png)

> [!NOTE]
> Wenn Sie das Direct Microsoft-Telefon-Routing-System verwenden, müssen Sie keine Anrufplanlizenz zuweisen.

Weitere Informationen finden Sie unter [Zuweisen von Lizenzen zu Benutzern.](/microsoft-365/admin/manage/assign-licenses-to-users)

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a>Schritt 3 - Eine Telefonnummer dem Benutzerkonto Telefon für gemeinsame Bereich zuweisen

Verwenden Sie Teams Admin Center, um dem Benutzer eine Nummer zuzuordnen.

1. Wählen Sie Teams Admin Center Sprachanrufnummern  >  **Telefon aus.**

3.    Wählen Sie eine Nummer aus der Liste der Telefonnummern aus und klicken Sie auf **Zuweisen**.

4. Geben Sie **auf** der Seite Zuweisen im Feld Sprachbenutzer den Namen des Benutzers ein, der  das Telefon verwenden soll, und wählen Sie den Benutzer dann in der Dropdownliste Sprachbenutzer auswählen aus.

5. Als Nächstes müssen Sie eine Notfalladresse hinzufügen. Wählen **Sie in der** Dropdownliste  Nach Ort **suchen,** Nach Beschreibung suchen oder Nach Ort suchen aus, und geben Sie dann den Ort, die Beschreibung oder den Ort in das Textfeld ein. Nach der Suche sehen Sie unter **Notfalladresse auswählen** nach, um die für Sie richtige Notfalladresse auszuwählen.

6. Klicken Sie auf **Speichern** und Ihr Benutzer sollte so aussehen:

   ![Screenshot mit Lizenzzuweisung](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> Benutzer werden nur dann anzeigen, wenn sie über eine Telefonsystem verfügen. Wenn Sie dies gerade erst getan haben, dann kann es etwas dauern, bis der Benutzer in der Liste erscheint.

Weitere Informationen finden Sie unter [Erhalten von Telefonnummern für Ihre Benutzer.](getting-phone-numbers-for-your-users.md)

Sie können auch Ihre telefonnummer, die Sie bei einem anderen Netzbetreiber haben, übertragen und "portieren" oder an Microsoft 365 oder Office 365. Weitere [Informationen finden Sie unter Übertragen von Telefonnummern Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).