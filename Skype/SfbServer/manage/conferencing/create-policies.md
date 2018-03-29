---
title: Erstellen von Konferenzrichtlinien in Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8c685326-8356-4075-bf95-32324b16ef81
description: 'Zusammenfassung: Informationen Sie zum Erstellen von konferenzrichtlinien in Skype für Business Server 2015.'
ms.openlocfilehash: 301474d57998d5c9a794a978c4ec8877b1e53bc7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="create-conferencing-policies-in-skype-for-business-server-2015"></a>Erstellen von Konferenzrichtlinien in Skype for Business Server 2015
 
**Zusammenfassung:** Informationen Sie zum Erstellen von konferenzrichtlinien in Skype für Business Server 2015.
  
Sie können konferenzrichtlinien mithilfe der Skype Business Server-Systemsteuerung oder mithilfe von Skype für Business Server-Verwaltungsshell erstellen.
  
## <a name="create-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Erstellen von konferenzrichtlinien mithilfe von Skype Business Server-Systemsteuerung

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2.  Öffnen von Skype Business Server-Systemsteuerung.
    
3. Klicken Sie auf der linken Navigationsleiste auf **Konferenzen** und anschließend auf **Konferenzrichtlinie**.
    
4. Klicken Sie auf **Neu** und führen Sie eine der folgenden Aktionen aus:
    
   - Klicken Sie auf **Hinzufügen**, um eine Richtlinie auf Benutzerebene zu erstellen. Geben Sie im Abschnitt **Neue Konferenzrichtlinie** bei **Name** einen beschreibenden Namen für die Richtlinie ein.
    
   - Klicken Sie auf **Standortrichtlinie**, um eine Richtlinie auf Standortebene zu erstellen. Geben Sie im Suchfeld **Standort auswählen** einen Teil oder den gesamten Namen des Standorts ein, für den Sie eine Richtlinie erstellen möchten. Klicken Sie in der Liste der Standorte auf den gewünschten Standort und klicken Sie auf **OK**.
    
    > [!NOTE]
    > Der Standortname wird als Name der Konferenzrichtlinie übernommen und kann nicht geändert werden. 
  
5. Geben Sie bei **Beschreibung** eine Beschreibung für die Richtlinie ein.
    
6. Geben Sie bei **Richtlinie für Organisatoren** unter **Maximale Besprechungsgröße** die Höchstzahl an Benutzern ein, die für eine Besprechung zugelassen werden sollen. Der maximale Besprechungsumfang ist standardmäßig auf 250 festgelegt.
    
7. Um Benutzer daran zu hindern, anonyme Benutzer zu Besprechungen einzuladen, deaktivieren Sie das Kontrollkästchen **Teilnehmer dürfen anonyme Benutzer einladen**. Anonyme Benutzer sind Benutzer, die keine Anmeldeinformationen in Ihrer Organisation Active Directory Domain Services, und wer, daher, nicht authentifiziert werden. In der Standardeinstellung können Benutzer anonyme Benutzer zu Besprechungen einladen.
    
8. Führen Sie im Abschnitt **Aufzeichnung** eine der folgenden Aktionen aus:
    
   - Klicken Sie auf **Keine**, um Teilnehmer an der Aufzeichnung von Besprechungen zu hindern. Dies ist die Standardeinstellung.
    
   - Klicken Sie auf **Aufzeichnung aktivieren**, um Teilnehmern die Aufzeichnung von Besprechungen zu gestatten.
    
9. Um externen Teilnehmern das Aufzeichnen von Besprechungen zu erlauben, aktivieren Sie das Kontrollkästchen **Partnerteilnehmern und anonymen Teilnehmern das Aufzeichnen gestatten**. In der Standardeinstellung werden externe Teilnehmer an der Aufzeichnung von Besprechungen gehindert.
    
10. Führen Sie im Abschnitt **Audio/Video** eine der folgenden Aktionen aus:
    
    - Klicken Sie auf **Keine**, um die Verwendung von Audio und Video zu verhindern.
    
    - Klicken Sie auf **IP-Audio aktivieren**, um die Verwendung von Audio, nicht jedoch von Video, zuzulassen.
    
    - Klicken Sie auf **IP-Audio/Video aktivieren**, um die Verwendung von Audio und Video zuzulassen. Dies ist die Standardeinstellung.
    
11. Wenn Sie die Verwendung von Audio im Abschnitt **Audio/Video** zulassen, führen Sie eine der folgenden Aufgaben aus:
    
    - Wenn Sie Benutzer daran hindern möchten, per Einwahl an einer Besprechung teilzunehmen, deaktivieren Sie das Kontrollkästchen **PSTN-Einwahlkonferenzen aktivieren**. In der Standardeinstellung können Benutzer sich über das Festnetz (Public Switched Telephone Network, PSTN) in Besprechungen einwählen.
    
    - Wenn Sie Benutzern die Einwahl in Besprechungen gestatten und nicht authentifizierten (anonymen) Benutzern die Teilnahme an Besprechungen über eine ausgehende Telefonverbindung erlauben möchten, aktivieren Sie das Kontrollkästchen **Anonyme Teilnehmer dürfen ausgehende Verbindungen herstelle**. Bei ausgehenden Telefonverbindungen ruft der Konferenzserver den Benutzer an und der Benutzer nimmt das Gespräch an, um an der Besprechung teilzunehmen. In der Standardeinstellung können anonyme Benutzer nicht über ausgehende Telefonverbindungen an Besprechungen teilnehmen.
    
12. Wenn Sie die Verwendung von Video im Abschnitt **Audio/Video** zulassen möchten, aktivieren Sie das Kontrollkästchen **Mehrere Videostreams zulassen**.
    
13. Führen Sie im Abschnitt **Datenzusammenarbeit** eine der folgenden Aktionen aus:
    
    - Wenn Sie keine Datenzusammenarbeit zulassen möchten, klicken Sie auf **Keine**.
    
    - Zum Zulassen einer Datenzusammenarbeit klicken Sie auf **Datenzusammenarbeit aktivieren**. Dies ist die Standardeinstellung.
    
14. Wenn Sie die Datenzusammenarbeit im Abschnitt **Datenzusammenarbeit** zulassen, führen Sie eine der folgenden Aufgaben aus:
    
    - Deaktivieren Sie das Kontrollkästchen **Partnerteilnehmer und anonyme Teilnehmer dürfen Inhalte herunterladen**. In der Standardeinstellung können externe Benutzer Inhalte herunterladen.
    
    - Deaktivieren Sie das Kontrollkästchen **Teilnehmer dürfen Dateien übertragen**, um Dateiübertragungen zu verhindern. In der Standardeinstellung können Dateien übertragen werden.
    
    - Deaktivieren Sie das Kontrollkästchen **Anmerkungen aktivieren**, um die Verwendung von Anmerkungen zu verhindern. Deaktivieren Sie das Kontrollkästchen **PowerPoint-Anmerkungen aktivieren**, um die Verwendung von Anmerkungen in freigegebenen PowerPoint-Präsentationen zu verhindern. In der Standardeinstellung sind Anmerkungen zulässig.
    
    - Deaktivieren Sie das Kontrollkästchen **Abstimmungen aktivieren**, um die Verwendung von Abstimmungen zu verhindern. In der Standardeinstellung sind Abstimmungen zulässig.
    
15. Führen Sie im Abschnitt **Anwendungsfreigabe** eine der folgenden Aktionen aus:
    
    - Klicken Sie auf **Anwendungsfreigabe deaktivieren**, um die Verwendung der Anwendungsfreigabe zu verhindern.
    
    - Klicken Sie auf **Anwendungsfreigabe aktivieren**, um die Verwendung der Anwendungsfreigabe zuzulassen. Dies ist die Standardeinstellung.
    
16. Wenn Sie die Anwendungsfreigabe im Abschnitt **Anwendungsfreigabe** zulassen, führen Sie eine der folgenden Aufgaben aus:
    
    - Deaktivieren Sie das Kontrollkästchen **Teilnehmer dürfen die Steuerung übernehmen**, um Teilnehmer an der Übernahme der Steuerung für die Anwendungsfreigabe zu hindern. In der Standardeinstellung können Teilnehmer die Steuerung für die Anwendungsfreigabe übernehmen.
    
    - Wenn Sie Besprechungsteilnehmern die Übernahme der Steuerung für die Anwendungsfreigabe ermöglichen möchten, aktivieren Sie das Kontrollkästchen **Partnerteilnehmer und anonyme Teilnehmer dürfen die Steuerung übernehmen**, um externen Benutzern die Übernahme der Steuerung für die Anwendungsfreigabe zu erlauben. In der Standardeinstellung können externe Benutzer die Steuerung für die Anwendungsfreigabe nicht übernehmen.
    
17. Führen Sie unter **Richtlinie für Teilnehmer** eine der folgenden Aktionen aus:
    
    - Klicken Sie auf **Anwendungs- und Desktopfreigabe deaktivieren**, um sowohl eine Anwendungsfreigabe als auch die Freigabe des Desktops zu verhindern.
    
    - Klicken Sie auf **Anwendungsfreigabe aktivieren**, um eine Anwendungsfreigabe, nicht jedoch die Freigabe des Desktops zu ermöglichen.
    
    - Klicken Sie auf **Anwendungs- und Desktopfreigabe aktivieren**, um sowohl eine Anwendungsfreigabe als auch die Freigabe des Desktops zuzulassen. Dies ist die Standardeinstellung.
    
18. Deaktivieren Sie das Kontrollkästchen **Peer-zu-Peer-Dateiübertragung aktivieren**, um Peer-zu-Peer-Dateiübertragungen zu verhindern. In der Standardeinstellung sind Peer-zu-Peer-Dateiübertragungen zulässig.
    
19. Aktivieren Sie das Kontrollkästchen **Peer-zu-Peer-Aufzeichnung aktivieren**, um eine Peer-zu-Peer-Aufzeichnung zuzulassen. In der Standardeinstellung sind Peer-zu-Peer-Aufzeichnungen unzulässig.
    
20. Aktivieren Sie das Kontrollkästchen **Teilnahme mit mehreren Videostreams aktivieren**, um die Teilnahme mit mehreren Videostreams zuzulassen. In der Standardeinstellung sind mehrere Videostreams zulässig.
    
21. Klicken Sie auf **Commit ausführen**.
    
## <a name="create-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Erstellen von konferenzrichtlinien mithilfe von Skype für Business Server-Verwaltungsshell

Verwenden Sie das Cmdlet **New-CsConferencingPolicy**, um Konferenzrichtlinien zu erstellen.
  
Das folgende Beispiel erstellt eine neue konferenzrichtlinie mit der Identität "salesconferencingpolicy" zu. Diese Richtlinie verwendet alle Standardwerte für eine Konferenzrichtlinie mit einer Ausnahme: MaxMeetingSize. In diesem Beispiel wird die maximale Besprechungsgröße statt auf den Standardwert 250 auf 50 festgelegt:
  
```
New-CsConferencingPolicy -Identity SalesConferencingPolicy -MaxMeetingSize 50
```

Weitere Informationen sowie eine Beschreibung für die vollständige Syntax und eine Liste der Parameter finden Sie unter [New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps).
  

