---
title: Erstellen oder Ändern einer Sprachrichtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e6ff27e0-e2d1-4445-840f-08f738200c20
description: 'Zusammenfassung: Erstellen oder Ändern von Sprachrichtlinien und Konfigurieren von PSTN-Verwendungsdatensätzen mithilfe der Skype for Business Server-Systemsteuerung.'
ms.openlocfilehash: 3e0fe5cebfc9d46f5c21554f1e18b54799d2d1e8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830405"
---
# <a name="create-or-modify-a-voice-policy-and-configure-pstn-usage-records-in-skype-for-business"></a>Erstellen oder Ändern einer Sprachrichtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in Skype for Business

**Zusammenfassung:** Erstellen oder Ändern von Sprachrichtlinien und Konfigurieren von PSTN-Verwendungsdatensätzen mithilfe der Skype for Business Server-Systemsteuerung.

> [!NOTE]
> Jeder Sprachrichtlinie muss mindestens ein Verwendungsdatensatz für das Festnetz (Public Switched Telephone Network, PSTN) zugeordnet sein. Eine Liste aller in Ihrer Enterprise-VoIP verfügbaren PSTN-Verwendungsdatensätze und deren Eigenschaften finden Sie unter Anzeigen von PSTN-Verwendungsdatensätzen [in Skype for Business.](view-pstn-usage-records.md)

### <a name="to-create-a-voice-policy"></a>So erstellen Sie eine VoIP-Richtlinie

1. Öffnen Sie die Skype for Business Server-Systemsteuerung.

2. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **VoIP-Richtlinie**.

3. Klicken Sie auf der Seite **VoIP-Richtlinie** auf **Neu**, und wählen Sie einen Bereich für die neue Richtlinie:

   - Eine **Standortrichtlinie** wird auf einen gesamten Standort angewendet, ausgenommen auf Benutzer oder Gruppen, die einer Benutzerrichtlinie zugeordnet wurden. Wenn Sie eine Richtlinie auf Standortebene erstellen möchten, wählen Sie den gewünschten Standort im Dialogfeld **Standort auswählen**. Wenn bereits eine VoIP-Richtlinie für einen Standort erstellt wurde, wird der Standort nicht im Dialogfeld **Standort auswählen** angezeigt.

   - Eine **Benutzerrichtlinie** kann auf bestimmte Benutzer oder Gruppen angewendet werden.

4. Wenn Sie eine VoIP-Richtlinie auf Benutzerebene erstellen, geben Sie im Feld **Name** einen beschreibenden Namen für die Richtlinie ein.

    > [!NOTE]
    > Bei Erstellung einer VoIP-Richtlinie auf Standortebene wird das Feld **Name** unter **Neue VoIP-Richtlinie** mit dem Standortnamen vorausgefüllt und kann nicht geändert werden.

5. (Optional) Geben Sie zusätzliche beschreibende Informationen zur VoIP-Richtlinie ein.

6. Aktivieren oder deaktivieren Sie die folgenden Kontrollkästchen, um die **Anruffunktionen** für diese VoIP-Richtlinie zu aktivieren oder zu deaktivieren:

   - **Voicemail** escape verhindert, dass Anrufe sofort an das Voicemailsystem des Mobiltelefons des Benutzers geroutet werden, wenn gleichzeitiges Klingeln konfiguriert ist und das Telefon ausgeschaltet, aus dem Akkustand oder nicht mehr verfügbar ist.

     > [!NOTE]
     > Diese Funktion kann nur über die Skype for Business Server-Verwaltungsshell konfiguriert werden.

   - **Anrufweiterleitung** ermöglicht Benutzern das Weiterleiten von Anrufen an andere Telefone und Clientgeräte. Skype for Business Server bietet eine deutlich breitere Palette von Konfigurationsoptionen für die Anruf weiterleitung. Wenn beispielsweise eine Organisation nicht möchte, dass eingehende Anrufe extern an das PSTN weitergeleitet werden, kann ein Administrator eine spezielle VoIP-Richtlinie geltend machen, um diese Einschränkung bereitzustellen. Diese Option ist standardmäßig aktiviert.

   - **Delegierung** ermöglicht Benutzern die Angabe anderer Benutzer, die in ihrem Namen Anrufe tätigen und empfangen können. In Skype for Business Server kann ein Stellvertreter gleichzeitiges Klingeln konfigurieren, das es eingehenden Anrufen an seinen Vorgesetzten ermöglicht, alle Ziele für gleichzeitiges Klingeln der Stellvertretung zu klingeln. Auf diese Weise kann der Stellvertreter flexibler auf die für seinen Manager bestimmten Anrufe reagieren. Diese Option ist standardmäßig aktiviert.

   - **Anrufdurchstellung** ermöglicht es, Anrufe an andere Benutzer durchzustellen. Diese Option ist standardmäßig aktiviert.

   - **Anruf parken** ermöglicht es Benutzern, Anrufe in der Warteschleife zu parken und den Anruf von einem anderen Telefon oder Client aus wiederaufzunehmen. Diese Option ist standardmäßig deaktiviert.

   - **Gleichzeitiges Klingeln** ermöglicht bei eingehenden Anrufen das gleichzeitige Klingeln auf zusätzlichen Telefonen (z. B. einem Mobiltelefon) oder anderen Endpunktgeräten. Skype for Business Server bietet eine deutlich breitere Palette von Konfigurationsoptionen für gleichzeitiges Klingeln. Diese Option ist standardmäßig aktiviert.

   - **Teamanruf** ermöglicht Benutzern in einem definierten Team die Annahme von Anrufen für andere Teammitglieder. Diese Option ist standardmäßig aktiviert.

   - **Durch** die umgeleitete Festnetzanrufe können Anrufe von Benutzern, denen diese Richtlinie zugewiesen ist, an andere Unternehmensbenutzer über das Telefonnetz umgeleitet werden, wenn das WAN überlastet oder nicht verfügbar ist. Diese Option ist standardmäßig aktiviert.

   - **Außerkraftsetzung der Bandbreitenrichtlinie** ermöglicht es Administratoren, Richtlinienentscheidungen im Rahmen der Anrufsteuerung für einen bestimmten Benutzer außer Kraft zu setzen. Diese Option ist standardmäßig deaktiviert.

     > [!NOTE]
     > Die Richtlinie wird nur für eingehende Anrufe an den Benutzer, nicht jedoch für ausgehende Anrufe außer Kraft gesetzt, die vom Benutzer getätigt werden. Nachdem die Sitzung hergestellt wurde, wird die Bandbreitenauslastung genau aufgezeichnet. Diese Einstellung sollte sparsam verwendet und für angemessene Entscheidungen der Anrufsteuerung reserviert werden.

   - **Die Nachverfolgung bösartiger** Anrufe ermöglicht Es Benutzern, böswillige Anrufe (z. B. Bedrohungen) mithilfe der Clientbenutzeroberfläche zu melden, die wiederum die Anrufe in den Anrufdetaildatensätzen (Call Detail Records, CDRs) kennzeichnet. Diese ist standardmäßig deaktiviert.

   - **Bei den Besetzt-Optionen** werden die Besetzt-Optionen für die angegebene Sprachrichtlinie aktiviert oder deaktiviert. Mit den Besetztoptionen können eingehende Anrufe an Voicemails geroutet oder mit einem Besetztzeichen abgelehnt werden, wenn sich der Zielbenutzer des Anrufs am Telefon befindet. "Gebucht"-Optionen ist eine neue Sprachrichtlinie, die im kumulativen Update vom Juli 2016 eingeführt wurde. Wenn Sie diesen Parameter aktivieren, werden die Beschäftigt-Optionen aktiviert, und die Option deaktiviert die Beschäftigt-Optionen. Weitere Informationen finden Sie unter [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md) und Install and configure Busy Options for Skype for Business [Server](install-and-configure-busy-options.md).

7. Führen Sie eine der folgenden Aktionen aus, um PSTN-Verwendungsdatensätze für diese VoIP-Richtlinie zuzuordnen und zu konfigurieren:

   - Klicken Sie auf **Auswählen**, um einen oder mehrere Datensätze aus einer Liste aller PSTN-Verwendungsdatensätze auszuwählen, die für Ihre Enterprise-VoIP-Bereitstellung zur Verfügung stehen. Markieren Sie die Datensätze, die Sie dieser VoIP-Richtlinie zuordnen möchten, und klicken Sie anschließend auf **OK**.

   - Markieren Sie einen Datensatz, und klicken Sie auf **Entfernen**, um einen PSTN-Verwendungsdatensatz aus der VoIP-Richtlinie zu entfernen.

   - Führen Sie die folgenden Schritte aus, um einen neuen PSTN-Verwendungsdatensatz zu definieren und dieser VoIP-Richtlinie zuzuordnen:

     a. Klicken Sie auf **Neu**.

     b. Geben Sie im Feld **Name** einen eindeutigen beschreibenden Namen für den Datensatz ein. Sie können z. B. einen PstN-Verwendungsdatensatz namensRedmond für Vollzeitmitarbeiter in Redmond und einen weiteren Eintrag mit dem Namen "RedmondTemps" für Zeitarbeiter erstellen.

     > [!NOTE]
     > Der Name des PSTN-Verwendungsdatensatzes muss innerhalb der Enterprise-VoIP-Bereitstellung eindeutig sein. Nach dem Speichern des Datensatzes kann das Feld **Name** nicht mehr bearbeitet werden.

     c. Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Datensatz zuzuordnen und zu konfigurieren:

   - Klicken Sie auf **Auswählen**, markieren Sie in der Liste der verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung eine oder mehrere gewünschte Routen, und klicken Sie dann auf **OK**.

   - Zum Entfernen einer Route aus dem PSTN-Verwendungseintrag markieren Sie die Route, und klicken Sie auf **Entfernen**.

   - Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungseintrag zuzuordnen. Weitere Informationen finden Sie unter ["Erstellen oder Ändern einer Sprachroute in Skype for Business".](create-or-modify-a-voice-route.md)

   - Markieren Sie die Route, und klicken Sie auf **Details anzeigen**, um eine Route zu bearbeiten, die diesem PSTN-Verwendungsdatensatz bereits zugeordnet wurde.

     d. Klicken Sie auf **OK**.

   - Führen Sie die folgenden Schritte aus, um einen PSTN-Verwendungsdatensatz zu bearbeiten, der bereits dieser VoIP-Richtlinie zugeordnet ist:

     a. Markieren Sie den PSTN-Verwendungseintrag, den Sie bearbeiten möchten, und klicken Sie auf **Details einblenden**.

     b. Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Datensatz zuzuordnen und zu konfigurieren:

   - Klicken Sie auf **Auswählen**, markieren Sie in der Liste der verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung eine oder mehrere gewünschte Routen, und klicken Sie dann auf **OK**.

   - Zum Entfernen einer Route aus diesem PSTN-Verwendungseintrag markieren Sie die Route, und klicken Sie auf **Entfernen**.

   - Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungseintrag zuzuordnen. Weitere Informationen finden Sie unter ["Erstellen oder Ändern einer Sprachroute in Skype for Business".](create-or-modify-a-voice-route.md)

   - Markieren Sie die Route, und klicken Sie auf **Details einblenden**, um eine Route zu bearbeiten, die diesem PSTN-Verwendungseintrag bereits zugeordnet wurde.

     c. Klicken Sie auf **OK**.

8. Ordnen Sie die PSTN-Verwendungseinträge zur Erzielung optimaler Leistung an. Wenn Sie die Position eines Datensatzes in der Liste ändern möchten, markieren Sie den Datensatznamen, und klicken Sie auf den Pfeil nach oben oder unten.

    > [!IMPORTANT]
    > Die Reihenfolge, in der die PstN-Verwendungseinträge in der Sprachrichtlinie aufgeführt werden, ist erheblich. Skype for Business Server durchläuft die Liste von oben nach unten. Es wird empfohlen, die Liste nach Verwendungshäufigkeit zu organisieren, z. B.: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.

9. Führen Sie eine der folgenden Aktionen aus, um PSTN-Verwendungsdatensätze für die Anrufweiterleitung und gleichzeitiges Klingeln in dieser VoIP-Richtlinie zuzuordnen und zu konfigurieren:

   - Um dieselben PSTN-Verwendungsdatensätze für die Anrufweiterleitung und gleichzeitiges Klingeln zu verwenden wie diese VoIP-Richtlinie, wählen Sie die Option **Mithilfe der gleichen PSTN-Verwendungen weiterleiten** im Dropdownmenü aus.

   - Wenn Sie nur interne Skype for Business-Benutzer anrufen und gleichzeitig klingeln können, wählen Sie die Option "Nur an interne **Skype for** Business-Benutzer weiterleiten" im Dropdownmenü aus. Anrufe werden nicht an externe PSTN-Nummern weitergeleitet.

   - Um andere PSTN-Verwendungseinträge für die Anrufweiterleitung und für das gleichzeitige Klingeln wie für diese VoIP-Richtlinie anzugeben, wählen Sie aus dem Dropdownmenü die Option **Mithilfe benutzerdefinierter PSTN-Verwendung weiterleiten** aus. Mit dieser Option wird ein Steuerelement angezeigt, um vorhandene PSTN-Verwendungseinträge auszuwählen oder um neue PSTN-Verwendungseinträge speziell für die Anrufweiterleitung und für das gleichzeitige Klingeln zu erstellen.

   - Klicken Sie auf **Auswählen**, um einen oder mehrere Einträge aus einer Liste von PSTN-Verwendungseinträgen für die Anrufweiterleitung und das gleichzeitige Klingeln auszuwählen. Markieren Sie die Einträge, die Sie dieser Richtlinie für die Anrufweiterleitung und das gleichzeitige Klingeln zuordnen möchten, und klicken Sie anschließend auf **OK**.

   - Markieren Sie einen Datensatz, und klicken Sie auf **Entfernen**, um einen PSTN-Verwendungsdatensatz aus dieser Richtlinie für die Anrufweiterleitung und gleichzeitiges Klingeln zu entfernen.

   - Führen Sie die folgenden Schritte aus, um einen neuen PSTN-Verwendungsdatensatz zu definieren und dieser Richtlinie für die Anrufweiterleitung und gleichzeitiges Klingeln zuzuordnen:

     a. Klicken Sie auf **Neu**.

     b. Geben Sie im Feld **Name** einen eindeutigen beschreibenden Namen für den Datensatz ein.

     > [!NOTE]
     > Der Name des PSTN-Verwendungsdatensatzes muss innerhalb der Enterprise-VoIP-Bereitstellung eindeutig sein. Nach dem Speichern des Datensatzes kann das Feld **Name** nicht mehr bearbeitet werden.

     c. Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Datensatz zuzuordnen und zu konfigurieren:

   - Klicken Sie auf **Auswählen**, markieren Sie in der Liste der verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung eine oder mehrere gewünschte Routen, und klicken Sie dann auf **OK**.

   - Zum Entfernen einer Route aus dem PSTN-Verwendungsdatensatz markieren Sie die Route, und klicken Sie auf **Entfernen**.

   - Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungsdatensatz zuzuordnen. Weitere Informationen finden Sie unter ["Erstellen oder Ändern einer Sprachroute in Skype for Business".](create-or-modify-a-voice-route.md)

   - Markieren Sie die Route, und klicken Sie auf **Details anzeigen**, um eine Route zu bearbeiten, die diesem PSTN-Verwendungsdatensatz bereits zugeordnet wurde.

     d. Klicken Sie auf **OK**.

   - Führen Sie die folgenden Schritte aus, um einen PSTN-Verwendungsdatensatz zu bearbeiten, der bereits dieser VoIP-Richtlinie zugeordnet ist:

     a. Markieren Sie den PSTN-Verwendungseintrag, den Sie bearbeiten möchten, und klicken Sie auf **Details einblenden**.

     b. Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Datensatz zuzuordnen und zu konfigurieren:

   - Klicken Sie auf **Auswählen**, markieren Sie in der Liste der verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung eine oder mehrere gewünschte Routen, und klicken Sie dann auf **OK**.

   - Zum Entfernen einer Route aus diesem PSTN-Verwendungsdatensatz markieren Sie die Route, und klicken Sie auf **Entfernen**.

   - Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungsdatensatz zuzuordnen. Weitere Informationen finden Sie unter ["Erstellen oder Ändern einer Sprachroute in Skype for Business".](create-or-modify-a-voice-route.md)

   - Markieren Sie die Route, und klicken Sie auf **Details anzeigen**, um eine Route zu bearbeiten, die diesem PSTN-Verwendungsdatensatz bereits zugeordnet wurde.

     c. Klicken Sie auf **OK**.

10. (Optional) Geben Sie eine Nummer zum Testen der VoIP-Richtlinie ein, und klicken Sie auf **Los**. Die Testergebnisse werden unter **Übersetzte Nummer für Test** angezeigt.

11. Klicken Sie auf **OK**.

12. Klicken Sie auf der Seite **VoIP-Richtlinie** auf **Commit**, und klicken Sie anschließend auf **Commit für alle**.

    > [!NOTE]
    > Jedes Mal, wenn Sie eine VoIP-Richtlinie erstellen oder ändern, müssen Sie den Befehl **Commit für alle Elemente ausführen** ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter [Veröffentlichen ausstehender Änderungen an der Voiceroutingkonfiguration in Skype for Business](voice-route-config-changes.md) in der Betriebsdokumentation.

13. (Optional) Voicemail escape detects that a call was immediately answered by the user's mobile phone voice mail, and disconnects the call to the mobile phone voice mail. Dadurch kann der Anruf weiterhin auf den anderen Endpunkten des Benutzers klingeln, was dem Benutzer die Möglichkeit gibt, den Anruf zu beantworten. Weitere Informationen zum Konfigurieren einer Voicemailrichtlinie finden Sie unter "Konfigurieren von Voicemail escape [in Skype for Business".](configure-voice-mail-escape.md)

### <a name="to-modify-a-voice-policy"></a>So ändern Sie eine VoIP-Richtlinie

1. Öffnen Sie die Skype for Business Server-Systemsteuerung.

2. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und anschließend auf **VoIP-Richtlinie**.

3. Doppelklicken Sie auf der Seite **VoIP-Richtlinie** auf den Namen einer VoIP-Richtlinie.

    > [!NOTE]
    > Der Bereich und der Name wurden bei Erstellung der VoIP-Richtlinie festgelegt. Sie können nicht geändert werden.

4. (Optional) Geben Sie in **VoIP-Richtlinie bearbeiten** zusätzliche Informationen zur Beschreibung der VoIP-Richtlinie ein.

5. Aktivieren oder deaktivieren Sie die folgenden Kontrollkästchen, um die einzelnen **Anruffunktionen** zu aktivieren bzw. zu deaktivieren:

   - **Voicemail** escape verhindert, dass Anrufe sofort an das Voicemailsystem des Mobiltelefons des Benutzers geroutet werden, wenn gleichzeitiges Klingeln konfiguriert ist und das Telefon ausgeschaltet, aus dem Akkustand oder nicht mehr verfügbar ist.

     > [!NOTE]
     > Diese Funktion kann nur über die Skype for Business Server-Verwaltungsshell konfiguriert werden.

   - **Anrufweiterleitung** ermöglicht Benutzern das Weiterleiten von Anrufen an andere Telefone und Clientgeräte. Skype for Business Server bietet eine deutlich breitere Palette von Konfigurationsoptionen für die Anruf weiterleitung. Wenn beispielsweise eine Organisation nicht möchte, dass eingehende Anrufe extern an das PSTN weitergeleitet werden, kann ein Administrator eine spezielle VoIP-Richtlinie geltend machen, um diese Einschränkung bereitzustellen. Diese Option ist standardmäßig aktiviert.

   - **Delegierung** ermöglicht Benutzern die Angabe anderer Benutzer, die in ihrem Namen Anrufe tätigen und empfangen können. In Skype for Business Server kann ein Stellvertreter gleichzeitiges Klingeln konfigurieren, das es eingehenden Anrufen an seinen Vorgesetzten ermöglicht, alle Ziele für gleichzeitiges Klingeln der Stellvertretung zu klingeln. Auf diese Weise kann der Stellvertreter flexibler auf die für seinen Manager bestimmten Anrufe reagieren. Diese Option ist standardmäßig aktiviert.

   - **Anrufdurchstellung** ermöglicht es, Anrufe an andere Benutzer durchzustellen. Diese Option ist standardmäßig aktiviert.

   - **Anruf parken** ermöglicht es Benutzern, Anrufe in der Warteschleife zu parken und den Anruf anschließend von einem anderen Telefon oder Client aus wiederaufzunehmen. Diese Option ist standardmäßig deaktiviert.

   - **Gleichzeitiges Klingeln** ermöglicht bei eingehenden Anrufen das gleichzeitige Klingeln auf zusätzlichen Telefonen (z. B. einem Mobiltelefon) oder anderen Endpunktgeräten. Skype for Business Server bietet eine deutlich breitere Palette von Konfigurationsoptionen für gleichzeitiges Klingeln. Diese Option ist standardmäßig aktiviert.

   - **Teamanruf** ermöglicht Benutzern in einem definierten Team die Annahme von Anrufen für andere Teammitglieder. Diese Option ist standardmäßig aktiviert.

   - **Durch** die umgeleitete Festnetzanrufe können Anrufe von Benutzern, denen diese Richtlinie zugewiesen ist, an andere Unternehmensbenutzer über das Telefonnetz umgeleitet werden, wenn das WAN überlastet oder nicht verfügbar ist. Diese Option ist standardmäßig aktiviert.

   - **Die Außerkraftsetzung von** Bandbreitenrichtlinien ermöglicht Administratoren das Außerkraft setzen von Richtlinienentscheidungen für die Automatische Systemauslastung für einen bestimmten Benutzer. Diese Option ist standardmäßig deaktiviert.

     > [!NOTE]
     > Die Richtlinie wird nur für eingehende Anrufe an den Benutzer, nicht jedoch für ausgehende Anrufe außer Kraft gesetzt, die vom Benutzer getätigt werden. Nachdem die Sitzung hergestellt wurde, wird die Bandbreitenauslastung genau aufgezeichnet. Diese Einstellung sollte sparsam verwendet werden.

   - **Die Nachverfolgung bösartiger** Anrufe ermöglicht Benutzern das Melden bösartiger Anrufe (z. B. Bedrohungen) mithilfe der Clientbenutzeroberfläche, die wiederum die Anrufe in den CdRs kennzeichnet. Diese Option ist standardmäßig deaktiviert.

6. Führen Sie eine der folgenden Aktionen aus, um PSTN-Verwendungsdatensätze für diese VoIP-Richtlinie zuzuordnen und zu konfigurieren:

   - Klicken Sie auf **Auswählen**, um einen oder mehrere Datensätze aus einer Liste aller PSTN-Verwendungsdatensätze auszuwählen, die für Ihre Enterprise-VoIP-Bereitstellung zur Verfügung stehen. Markieren Sie die Datensätze, die Sie dieser VoIP-Richtlinie zuordnen möchten, und klicken Sie anschließend auf **OK**.

   - Markieren Sie einen Datensatz, und klicken Sie auf **Entfernen**, um einen PSTN-Verwendungsdatensatz aus der VoIP-Richtlinie zu entfernen.

   - Führen Sie die folgenden Schritte aus, um einen neuen PSTN-Verwendungsdatensatz zu definieren und dieser VoIP-Richtlinie zuzuordnen:

     a. Klicken Sie auf **Neu**.

     b. Geben Sie im Feld **Name** einen eindeutigen beschreibenden Namen für den Datensatz ein. Sie können z. B. einen PstN-Verwendungsdatensatz namens "Redmond" für Vollzeitmitarbeiter in Redmond und einen weiteren Eintrag namens "RedmondTemps" für Zeitarbeiter erstellen.

     > [!NOTE]
     > Der Name des PSTN-Verwendungsdatensatzes muss innerhalb der Enterprise-VoIP-Bereitstellung eindeutig sein. Nach dem Speichern des Datensatzes kann das Feld **Name** nicht mehr bearbeitet werden.

     c. Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Datensatz zuzuordnen und zu konfigurieren:

   - Klicken Sie auf **Auswählen**, markieren Sie in der Liste der verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung eine oder mehrere gewünschte Routen, und klicken Sie dann auf **OK**.

   - Zum Entfernen einer Route aus dem PSTN-Verwendungsdatensatz markieren Sie die Route, und klicken Sie auf **Entfernen**.

   - Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungsdatensatz zuzuordnen. Weitere Informationen finden Sie unter ["Erstellen oder Ändern einer Sprachroute in Skype for Business".](create-or-modify-a-voice-route.md)

   - Markieren Sie die Route, und klicken Sie auf **Details anzeigen**, um eine Route zu bearbeiten, die diesem PSTN-Verwendungsdatensatz bereits zugeordnet wurde.

     d. Klicken Sie auf **OK**.

   - Führen Sie die folgenden Schritte aus, um einen PSTN-Verwendungsdatensatz zu bearbeiten, der bereits dieser VoIP-Richtlinie zugeordnet ist:

     a. Markieren Sie den PSTN-Verwendungsdatensatz, den Sie bearbeiten möchten, und klicken Sie auf **Details anzeigen**.

     b. Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Datensatz zuzuordnen und zu konfigurieren:

   - Klicken Sie auf **Auswählen**, markieren Sie in der Liste der verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung eine oder mehrere gewünschte Routen, und klicken Sie dann auf **OK**.

   - Zum Entfernen einer Route aus diesem PSTN-Verwendungsdatensatz markieren Sie die Route, und klicken Sie auf **Entfernen**.

   - Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungsdatensatz zuzuordnen. Weitere Informationen finden Sie unter ["Erstellen oder Ändern einer Sprachroute in Skype for Business".](create-or-modify-a-voice-route.md)

   - Markieren Sie die Route, und klicken Sie auf **Details anzeigen**, um eine Route zu bearbeiten, die diesem PSTN-Verwendungsdatensatz bereits zugeordnet wurde.

     c. Klicken Sie auf **OK**.

7. Ordnen Sie die PSTN-Verwendungseinträge zur Erzielung optimaler Leistung an. Wenn Sie die Position eines Datensatzes in der Liste ändern möchten, markieren Sie den Datensatznamen, und klicken Sie auf den Pfeil nach oben oder unten.

    > [!NOTE]
    > Die Reihenfolge, in der die PstN-Verwendungseinträge in der Sprachrichtlinie aufgeführt werden, ist erheblich. Skype for Business Server durchläuft die Liste von oben nach unten. Es wird empfohlen, die Liste nach Verwendungshäufigkeit zu organisieren, z. B.: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.

8. Führen Sie eine der folgenden Aktionen aus, um PSTN-Verwendungsdatensätze für die Anrufweiterleitung und gleichzeitiges Klingeln in dieser VoIP-Richtlinie zuzuordnen und zu konfigurieren:

   - Um dieselben PSTN-Verwendungsdatensätze für die Anrufweiterleitung und gleichzeitiges Klingeln zu verwenden wie diese VoIP-Richtlinie, wählen Sie die Option **Mithilfe der gleichen PSTN-Verwendungen weiterleiten** im Dropdownmenü aus.

   - Wenn Sie die Anrufanrufanrufe und gleichzeitiges Klingeln nur für interne Skype for Business-Benutzer zulassen, wählen Sie **"An** interne Skype for Business-Benutzer weiterleiten" nur im Dropdownmenü aus. Die Anrufe werden dann nicht an externe PSTN-Nummern weitergeleitet.

   - Um andere PSTN-Verwendungsdatensätze für die Anrufweiterleitung und gleichzeitiges Klingeln zu verwenden, als die für diese VoIP-Richtlinie verwendeten, wählen Sie die Option **Mithilfe benutzerdefinierter PSTN-Verwendungen weiterleiten** im Dropdownmenü aus. Bei Auswahl dieser Option wird ein Steuerelement angezeigt, über das vorhandene PSTN-Verwendungsdatensätze ausgewählt oder neue PSTN-Verwendungsdatensätze erstellt werden können, die speziell auf die Anrufweiterleitung und gleichzeitiges Klingeln ausgerichtet sind.

   - Klicken Sie auf **Auswählen**, um einen oder mehrere Datensätze aus einer Liste aller PSTN-Verwendungsdatensätze für die Anrufweiterleitung und gleichzeitiges Klingeln auszuwählen. Markieren Sie die Datensätze, die Sie der Richtlinie für die Anrufweiterleitung und gleichzeitiges Klingeln zuordnen möchten, und klicken Sie anschließend auf **OK**.

   - Markieren Sie einen Datensatz, und klicken Sie auf **Entfernen**, um einen PSTN-Verwendungsdatensatz aus dieser Richtlinie für die Anrufweiterleitung und gleichzeitiges Klingeln zu entfernen.

   - Führen Sie die folgenden Schritte aus, um einen neuen PSTN-Verwendungsdatensatz zu definieren und dieser Richtlinie für die Anrufweiterleitung und gleichzeitiges Klingeln zuzuordnen:

     a. Klicken Sie auf **Neu**.

     b. Geben Sie im Feld **Name** einen eindeutigen beschreibenden Namen für den Datensatz ein.

     > [!NOTE]
     > Der Name des PSTN-Verwendungsdatensatzes muss innerhalb der Enterprise-VoIP-Bereitstellung eindeutig sein. Nach dem Speichern des Datensatzes kann das Feld **Name** nicht mehr bearbeitet werden.

     c. Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Datensatz zuzuordnen und zu konfigurieren:

   - Klicken Sie auf **Auswählen**, markieren Sie in der Liste der verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung eine oder mehrere gewünschte Routen, und klicken Sie dann auf **OK**.

   - Zum Entfernen einer Route aus dem PSTN-Verwendungsdatensatz markieren Sie die Route, und klicken Sie auf **Entfernen**.

   - Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungsdatensatz zuzuordnen. Weitere Informationen finden Sie unter ["Erstellen oder Ändern einer Sprachroute in Skype for Business".](create-or-modify-a-voice-route.md)

   - Markieren Sie die Route, und klicken Sie anschließend auf **Details anzeigen**, um eine Route zu bearbeiten, die diesem PSTN-Verwendungsdatensatz bereits zugeordnet wurde. Ausführliche Informationen erhalten Sie im Abschnitt [Modify a Voice Route](https://technet.microsoft.com/library/afc562cc-8807-489b-8850-dbbe1c1ab9f5.aspx).

     d. Klicken Sie auf **OK**.

   - Führen Sie die folgenden Schritte aus, um einen PSTN-Verwendungsdatensatz zu bearbeiten, der bereits dieser VoIP-Richtlinie zugeordnet ist:

     a. Markieren Sie den PSTN-Verwendungsdatensatz, den Sie bearbeiten möchten, und klicken Sie auf **Details anzeigen**.

     b. Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Datensatz zuzuordnen und zu konfigurieren:

     - Klicken Sie auf **Auswählen**, markieren Sie in der Liste der verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung eine oder mehrere gewünschte Routen, und klicken Sie dann auf **OK**.

     - Zum Entfernen einer Route aus diesem PSTN-Verwendungsdatensatz markieren Sie die Route, und klicken Sie auf **Entfernen**.

     - Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungsdatensatz zuzuordnen. Weitere Informationen finden Sie unter ["Erstellen oder Ändern einer Sprachroute in Skype for Business".](create-or-modify-a-voice-route.md)

     - Markieren Sie die Route, und klicken Sie auf **Details anzeigen**, um eine Route zu bearbeiten, die diesem PSTN-Verwendungsdatensatz bereits zugeordnet wurde. Ausführliche Informationen finden Sie unter [Modify a Voice Route](https://technet.microsoft.com/library/afc562cc-8807-489b-8850-dbbe1c1ab9f5.aspx).

     c. Klicken Sie auf **OK**.

9. (Optional) Geben Sie eine Nummer zum Testen der VoIP-Richtlinie ein, und klicken Sie auf **Los**. Die Testergebnisse werden unter **Übersetzte Nummer für Test** angezeigt.

10. Klicken Sie auf **OK**.

11. Klicken Sie auf der Seite **VoIP-Richtlinie** auf **Commit**, und klicken Sie anschließend auf **Commit für alle**.

    > [!NOTE]
    > Jedes Mal, wenn Sie eine VoIP-Richtlinie erstellen oder ändern, müssen Sie den Befehl **Commit für alle** ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter [Veröffentlichen ausstehender Änderungen an der Voiceroutingkonfiguration in Skype for Business](voice-route-config-changes.md) in der Betriebsdokumentation.

12. (Optional) Voicemail escape detects that a call was immediately answered by the user's mobile phone voice mail, and disconnects the call to the mobile phone voice mail. Dadurch kann der Anruf weiterhin auf den anderen Endpunkten des Benutzers klingeln, was dem Benutzer die Möglichkeit gibt, den Anruf zu beantworten. Weitere Informationen zum Konfigurieren einer Voicemailrichtlinie finden Sie unter Konfigurieren von [Voicemail](configure-voice-mail-escape.md)escape in Skype for Business .

## <a name="see-also"></a>Siehe auch

[Anzeigen von PSTN-Verwendungsdatensätzen in Skype for Business](view-pstn-usage-records.md)

[Erstellen oder Ändern einer Sprachroute in Skype for Business](create-or-modify-a-voice-route.md)

[Veröffentlichen ausstehender Änderungen an der Voiceroutingkonfiguration in Skype for Business](voice-route-config-changes.md)

[Konfigurieren von Voicemail escape in Skype for Business](configure-voice-mail-escape.md)

