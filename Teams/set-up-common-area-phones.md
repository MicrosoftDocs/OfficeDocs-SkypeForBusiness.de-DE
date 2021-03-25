---
title: Einrichten der Common Area Phone-Lizenz
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
> Telefone im allgemeinen Bereich unterstützen keine Voicemail.

Ein Telefon im allgemeinen Bereich wird in der Regel in einem Bereich wie einem Wartebereich oder einem anderen Bereich platziert, der vielen Personen zum Anrufen zur Verfügung steht. beispielsweise einen Empfangsbereich, einen Wartebereich oder ein Konferenztelefon. Telefone im allgemeinen Bereich sind mit Konten angemeldet, die an eine Common Area Phone-Lizenz gebunden sind. Die TeamsIPPhone-Richtlinie muss auch entsprechend festgelegt sein, damit das Telefon über eine allgemeine Benutzererfahrung verfügt.

In den nachstehenden Schritten helfen wir Ihnen bei der Einrichtung eines Kontos für Telefonsystem zum Bereitstellen von Telefonen im allgemeinen Bereich für Ihre Organisation. Für eine vollständigere Besprechungsraumerfahrung, einschließlich Audiokonferenzen, sollten Sie die dedizierte Lizenz für Den Besprechungsraum mit einem Besprechungsraumgerät erwerben. 

Zuerst müssen Sie eine Common Area Phone (CAP)-Lizenz erwerben und sicherstellen, dass Sie über ein zertifiziertes Telefon verfügen. Weitere Informationen zu zertifizierten Telefonen finden Sie unter [Microsoft Teams-Geräte.](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1) 

## <a name="step-1---buy-the-licenses"></a>Schritt 1 - Lizenzen kaufen

1. Wechseln Sie im Microsoft 365 Admin Center zu  >  **Abrechnungskaufdienste,** und erweitern Sie dann **Andere Pläne.**

    ![Screenshot der Kachel "Common Area Phone"](media/set-up-common-area-phone-image1.png)

2. Wählen **Sie Jetzt telefon kaufen** im allgemeinen Bereich  >  **aus.**

3. Klicken Sie auf der Seite Auschecken auf **Jetzt kaufen.**

4. Erweitern **Sie Add-On-Abonnements,** und klicken Sie dann, um einen Anrufplan zu kaufen. Wählen Sie entweder den **Plan für Inlandsrufe oder** den Plan für **Inlands- und Auslandsrufe aus.**

> [!NOTE]
> Wenn Sie Microsoft Phone System Direct Routing verwenden, benötigen Sie keine Lizenz für Anrufplan.

> [!NOTE]
> Sie müssen keine Telefonsystemlizenz hinzufügen. Sie ist in der Lizenz Telefon für gemeinsame Bereiche enthalten.

Weitere Informationen zu Lizenzen finden Sie unter [Microsoft Teams-Add-On-Lizenzierung](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

Die Common Area Phone-Lizenz unterstützt: 


|   |  Telefon für gemeinsame Bereiche  |
|---------|---------|
|Skype for Business |   &#x2714; |
|Microsoft Teams |   &#x2714; |
|Telefonsystem |    &#x2714; |
|Audiokonferenzen |       &#x2718; &Sup1;  |
|Microsoft Intune |    &#x2718; |
|Weltweite Verfügbarkeit |       &#x2718; &sup2;  |
|Kanalverfügbarkeit |    EA, EAS, CSP, GCC, EES, Web Direct  |
|      |         |

&Sup1; Telefone im allgemeinen Bereich können über die vom Besprechungsorganisator bereitgestellte Einwahlnummer an Audiokonferenzen teilnehmen.

&sup2; In souveränen Wolken nicht verfügbar  



## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>Schritt 2 - Ein neues Benutzerkonto für das Telefon erstellen und die Lizenzen zuweisen

1. Wechseln Sie im Microsoft 365 Admin Center zu Benutzer, die  >  **aktive Benutzer einen** Benutzer  >  **hinzufügen.**

2. Geben Sie einen Benutzernamen wie "Main" für den Vornamen und "Empfang" für den zweiten Namen ein.

3. Geben Sie einen Anzeigenamen ein, wenn er nicht automatisch generiert wird, z. B. "Hauptempfang".

4. Geben Sie einen Benutzernamen wie "MainRezeption" oder "Mainlobby" ein.

5. Bei Telefonen im allgemeinen Bereich können Sie ein Kennwort manuell festlegen oder dasselbe Kennwort für alle Telefone im allgemeinen Bereich verwenden. Außerdem sollten Sie das Kontrollkästchen Benutzer beim ersten Anmelden zum Ändern des Kennworts durch **diesen** Benutzer aktivieren.

6. Weisen Sie dem Benutzer die Lizenzen zu. Klicken Sie auf der gleichen Seite auf **Produktlizenzen** erweitern. Aktivieren Sie das Telefon im allgemeinen Bereich, und wählen Sie **entweder** einen Plan für Inlandsanrufe oder einen Plan für Inlands- und **Auslandsanrufe aus.** 

    ![Screenshot der Lizenzzuweisung](media/set-up-common-area-phone-image2.png)

> [!NOTE]
> Wenn Sie Microsoft Phone System Direct Routing verwenden, müssen Sie keine Lizenz für den Anrufplan zuweisen.

Weitere Informationen finden Sie unter [Zuweisen von Lizenzen zu Benutzern.](/microsoft-365/admin/manage/assign-licenses-to-users)

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a>Schritt 3 - Eine Telefonnummer dem Benutzerkonto Telefon für gemeinsame Bereich zuweisen

Verwenden Sie das Teams Admin Center, um dem Benutzer eine Nummer zuzuordnen.

1. Wählen Sie im Teams Admin Center voice  >  **phone numbers aus.**

3.    Wählen Sie eine Nummer aus der Liste der Telefonnummern aus und klicken Sie auf **Zuweisen**.

4. Geben Sie **auf** der Seite Zuweisen im Feld Sprachbenutzer den Namen des Benutzers ein, der  das Telefon verwenden soll, und wählen Sie dann den Benutzer in der Dropdownliste Sprachbenutzer auswählen aus.

5. Als Nächstes müssen Sie eine Notfalladresse hinzufügen. Wählen **Sie in der** Dropdownliste  Nach Ort, Beschreibung suchen oder Nach Ort suchen aus, und geben Sie dann den Ort, die Beschreibung oder den Ort in das Textfeld ein.  Nachdem Sie gesucht haben, suchen Sie unter **Notfalladresse auswählen,** um die richtige Notfalladresse für Sie auszuwählen.

6. Klicken Sie auf **Speichern** und Ihr Benutzer sollte so aussehen:

   ![Screenshot der Lizenzzuweisung](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> Benutzer werden nur dann anzeigen, wenn eine Telefonsystemlizenz angewendet wurde. Wenn Sie dies gerade erst getan haben, dann kann es etwas dauern, bis der Benutzer in der Liste erscheint.

Weitere Informationen finden Sie unter [Abrufen von Telefonnummern für Ihre Benutzer.](getting-phone-numbers-for-your-users.md)

Sie können Auch Ihre Telefonnummer, die Sie bei einem anderen Netzbetreiber haben, und "portieren" oder an Microsoft 365 oder Office 365 übertragen. Weitere [Informationen finden Sie unter Übertragen von Telefonnummern an Teams.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)