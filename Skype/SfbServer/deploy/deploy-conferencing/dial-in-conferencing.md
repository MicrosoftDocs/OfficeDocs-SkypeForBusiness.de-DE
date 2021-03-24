---
title: Konfigurieren von Einwahlkonferenzen in Skype for Business Server
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
ms.assetid: 38d9f168-80b8-46f2-a1c0-becd84e58e73
description: 'Zusammenfassung: In diesem Thema erfahren Sie, wie Sie Einwahlkonferenzen in Skype for Business Server konfigurieren.'
ms.openlocfilehash: 5f618e22cc45585baddf1e8d6090b9e211dc5681
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103851"
---
# <a name="configure-dial-in-conferencing-in-skype-for-business-server"></a>Konfigurieren von Einwahlkonferenzen in Skype for Business Server
 
**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie Einwahlkonferenzen in Skype for Business Server konfigurieren.
  
Nachdem Sie eine Topologie erstellt haben, die die Konferenzarbeitsauslastung und ausgewählte Einwahlkonferenzen umfasst, müssen Sie zusätzliche Schritte zum Konfigurieren von Einwahlkonferenzen ausführen. Bevor Sie dieses Thema lesen, stellen Sie sicher, dass Sie plan [for dial-in conferencing in Skype for Business Server,](../../plan-your-deployment/conferencing/dial-in-conferencing.md) [Hardware-](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md)und Softwareanforderungen für Konferenzen in Skype for Business Server sowie das [Bereitstellungsflussdiagramm](deploy-conferencing.md#deployment-flowchart-and-checklist-for-dial-in-conferencing)und die Prüfliste für Einwahlkonferenzen gelesen haben. 
  
Zum Konfigurieren von Einwahlkonferenzen müssen Sie die folgenden Aufgaben ausführen:
  
- [Konfigurieren von Wähleinstellungen](dial-in-conferencing.md#BKMK_ConfigureDialPlans)
    
- [Konfigurieren von Einwahlkonferenzregionen](dial-in-conferencing.md#BKMK_ConfigureDialInRegions)
    
- [Konfigurieren von Zugriffsnummern für die Einwahl](dial-in-conferencing.md#BKMK_ConfigureDialInAccessNumbers)
    
- [Konfigurieren von Konferenzrichtlinien](dial-in-conferencing.md#BKMK_ConfigureConferencingPolicies)
    
- [Zuweisen eines Zeilen-URI zu einem Benutzerkonto](dial-in-conferencing.md#BKMK_AssignaLineURI)
    
Darüber hinaus können Sie die folgenden optionalen Aufgaben ausführen. Weitere Informationen zu diesen [optionalen](../../manage/conferencing/dial-in-conferencing.md)Aufgaben finden Sie unter Verwalten von Einwahlkonferenzen in Skype for Business Server .
  
- Verwalten von PIN-Richtlinien für Einwahlkonferenzen
    
- Verwalten der Schlüsselzuordnung für DTMF-Befehle
    
- Erstellen von Konferenzverzeichnissen
    
- Verwalten von Ankündigungen zum Beitreten und Verlassen von Konferenzkonferenzen
    
- Testen der Einstellungen für Einwahlkonferenzen
    
- Senden von Willkommens-E-Mails an Einwahlbenutzer
    
## <a name="configure-dial-plans"></a>Konfigurieren von Wähleinstellungen
<a name="BKMK_ConfigureDialPlans"> </a>

Bei der Bereitstellung von Einwahlkonferenzen müssen Sie einen oder mehrere Sätze mit Wähleinstellungen zum Routen von Zugriffsnummern für die Einwahl erstellen oder ändern. Außerdem müssen Sie sicherstellen, dass jeder Wählplan mindestens eine Normalisierungsregel enthält – eine Regel, die Telefonerweiterungen in vollständige Telefonnummern im E.164-Format konvertiert. 
  
Benutzer von Einwahlkonferenzen nehmen an Konferenzen als authentifizierte Unternehmensbenutzer teil, indem sie ihre PIN und die Telefonnummer eingeben. Sie benötigen eine Normalisierungsregel zum Konvertieren von Durchwahlen in vollständige Rufnummern, damit Benutzer bei Eingabe einer Durchwahl authentifiziert werden können.
  
So richten Sie Wählpläne für Einwahlkonferenzen ein:
  
- Unabhängig davon, ob Sie Enterprise-VoIP bereitstellen, ändern Sie den globalen Wählplan, um einen Einwahlkonferenzbereich hinzuzufügen und sicherzustellen, dass ihre Einwahlnummern durch eine Normalisierungsregel korrekt konvertiert werden. Ausführliche Anweisungen finden Sie unter Erstellen oder Ändern [eines Wählplans in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).
    
- Wenn Sie keine Enterprise-VoIP, erstellen Sie Wählpläne für Ihre Zugriffsnummern für Einwahlkonferenzen. Stellen Sie sicher, dass Sie eine Region für Einwahlkonferenzen angeben. Ausführliche Anweisungen finden Sie unter Erstellen oder Ändern [eines Wählplans in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).
    
- Wenn Sie Enterprise-VoIP, ändern Enterprise-VoIP Wähleinstellungen nach Bedarf, um Regionen zu enthalten und geeignete Normalisierungsregeln für Einwahlnummern zu verwenden. Sie können auch dedizierte Wähleinstellungen erstellen, die nur für Zugriffsnummern für die Einwahl eingesetzt werden. Ausführliche Anweisungen finden Sie unter Erstellen oder Ändern [eines Wählplans in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).
    
Weitere Informationen zum Erstellen von Normalisierungsregeln finden Sie unter Erstellen oder Ändern einer Normalisierungsregel [in Skype for Business](../../deploy/deploy-enterprise-voice/normalization-rules.md).
  
## <a name="configure-dial-in-conferencing-regions"></a>Konfigurieren von Einwahlkonferenzregionen
<a name="BKMK_ConfigureDialInRegions"> </a>

Wenn Sie einen Satz mit Wähleinstellungen einrichten, geben Sie die Region für Einwahlkonferenzen an, die für diese Wähleinstellungen gilt. Die Einwahlkonferenzregion ordnet Zugriffsnummern für Einwahlkonferenzen dem entsprechenden Wählplan zu. Wenn Sie anschließend die Zugriffsnummern für Einwahlkonferenzen erstellen, wählen Sie die Regionen aus, welche die Zugriffsnummern den geeigneten Wähleinstellungen zuordnen. 
  
Da es wichtig ist, eine Region für alle Wählpläne anzugeben, sollten Sie überprüfen, ob alle Wählpläne Konferenzregionen haben. 
  
Verwenden Sie das **Cmdlet Get-CsDialPlan,** um zu überprüfen, ob die Region für alle Einwahlkonferenzpläne festgelegt ist. Wenn die Region in einem Satz mit Wähleinstellungen fehlt, können Sie die Region mit dem Cmdlet **Set-CsDialPlan** festlegen. Sie können auch die Skype for Business Server-Systemsteuerung verwenden, um die Region in vorhandenen Wählplänen zu aktualisieren. Weitere Informationen zur Verwendung der Skype for Business Server-Systemsteuerung finden Sie unter Erstellen oder Ändern eines Wählplans [in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).
  
### <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a>So überprüfen Sie, ob für Wähleinstellungen die Region festgelegt wurde

1. Melden Sie sich beim Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** oder **CsAdministrator** an.
    
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start,** klicken Sie auf **Alle Programme,** **klicken Sie auf Skype for Business 2015,** und klicken Sie dann auf **Skype for Business Server Management Shell**.
    
3. Führen Sie den folgenden Befehl an der Eingabeaufforderung aus:
    
   ```powershell
   Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
   ```

   Beispiel:
    
   ```powershell
   Get-CsDialPlan
   ```

   In diesem Beispiel werden alle für Ihre Organisation konfigurierten Wähleinstellungen zurückgegeben.
    
4. Überprüfen Sie die zurückgegebenen Wähleinstellungen, um fehlende Regionen für Einwahlkonferenzen zu ermitteln. 
    
Weitere Informationen finden Sie unter [Get-CsDialPlan](/powershell/module/skype/get-csdialplan?view=skype-ps).
  
### <a name="to-set-the-region-property-for-a-dial-plan"></a>So legen Sie die Region für einen Satz mit Wähleinstellungen fest

1. Melden Sie sich beim Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** oder **CsAdministrator** an.
    
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start,** klicken Sie auf **Alle Programme,** **klicken Sie auf Skype for Business 2015,** und klicken Sie dann auf **Skype for Business Server Management Shell**.
    
3. Führen Sie für alle Wähleinstellungen, in denen die Region für Einwahlkonferenzen fehlt, den folgenden Befehl aus:
    
   ```powershell
   Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
   ```

   Beispiel:
    
   ```powershell
   Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
   ```

   In diesem Beispiel wird die Eigenschaft "DialinConferencingRegion" in den Wähleinstellungen mit der Identität "Redmond" in den Wert "US West Coast" geändert. 
    
Weitere Informationen finden Sie unter [Set-CsDialPlan](/powershell/module/skype/set-csdialplan?view=skype-ps).
  
## <a name="configure-dial-in-access-numbers"></a>Konfigurieren von Zugriffsnummern für die Einwahl
<a name="BKMK_ConfigureDialInAccessNumbers"> </a>

Beim Bereitstellen von Einwahlkonferenzen müssen Sie Telefonnummern einrichten, die Benutzer aus dem Telefonfestnetz (Public Switched Telephone Network, PSTN) wählen können, um am Audioteil einer Konferenz teilzunehmen. Diese Zugriffsnummern für die Einwahl werden in Besprechungseinladungen und auf der Webseite mit den Einstellungen für Einwahlkonferenzen angezeigt.
  
Vor dem Erstellen von Zugriffsnummern für die Einwahl müssen Sie zunächst die Regionen Ihrer Einwahlkonferenzen planen und anschließend Wählpläne für die Regionen konfigurieren. Weitere Informationen zu Regionen finden Sie unter [Plan for Dial-in conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md). Weitere Informationen zum Konfigurieren von Wählplänen für Einwahlkonferenzen finden Sie unter Erstellen oder Ändern eines Wählplans [in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).
  
> [!NOTE]
> Sie können eine neue Zugriffsnummer erst dann für Einwahlkonferenzen verwenden, wenn die Replikation der Active Directory-Domänendienste (AD DS) für diese Zugriffsnummer abgeschlossen ist. Die Replikation kann mehrere Stunden in Anspruch nehmen. 
  
> [!NOTE]
> Nach dem Erstellen von Zugriffsnummern für die Einwahl können Sie den Anzeigenamen für die Active Directory-Kontaktobjekte modifizieren, sodass Benutzer die richtige Zugriffsnummer einfacher identifizieren können. Verwenden Sie zum Ändern des Anzeigenamens das [Cmdlet Set-CsDialInConferencingAccessNumber.](/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) Active Directory-Objekte sollten nicht manuell geändert werden.
  
### <a name="to-create-a-dial-in-access-number"></a>So erstellen Sie eine Einwahlnummer

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **Konferenz** und dann auf **Zugriffsnummer für Einwahl**.
    
4. Gehen Sie auf der **Seite** Einwahlzugriffsnummer wie folgt vor:
    
   - Klicken **Sie auf Neu,** um **neue Einwahlzugriffsnummer zu öffnen.**
    
   - Klicken Sie auf eine der Einwahlnummern in der Liste, klicken Sie auf **Bearbeiten** und dann **auf Details anzeigen.**
    
     > [!NOTE]
     > Die Verwendung des Suchfelds zum Suchen nach dem Inhalt einer Spalte in der Liste der Einwahlnummern führt möglicherweise nicht zu den von Ihnen erwarteten Ergebnissen. Sortieren Sie stattdessen die Liste nach der Spalte von Interesse, um die Einwahlnummer zu identifizieren, die Sie anzeigen oder ändern möchten. 
  
5. Geben **Sie unter** Anzeigenummer die Telefonnummer ein, die Telefonbenutzer im Telefonnetz (Public Switched Telephone Network, PSTN) wählen, um an einer Konferenz teilnehmen zu können. Diese Nummer wird in Besprechungseinladungen und auf der Webseite "Einstellungen für Einwahlkonferenzen" angezeigt.
    
6. Geben **Sie unter** Anzeigename eine Beschreibung für die Einwahlzugriffsnummer ein. Dies ist der Name, der der Einwahlzugriffsnummer in den Skype for Business-Suchergebnissen zugeordnet ist. Dieser Name wird im Client angezeigt, wenn ein Benutzer die Zugriffsnummer aufruft. 
    
7. Geben **Sie im Zeilen-URI** die E.164-Nummer der Einwahlnummer im TEL-URI-Format ein, einschließlich des +-Symbols vor der Nummer und ohne Leerzeichen. Beispiel: tel:+14255550200.
    
    > [!NOTE]
    > Der gleiche Zeilen-URI kann nicht von einer anderen Zugriffsnummer für Einwahlkonferenzen wiederverwendet werden. 
  
8. Gehen **Sie in SIP-URI** wie folgt vor:
    
   - Geben Sie in das Textfeld einen eindeutigen SIP-URI für diese Zugriffsnummer für Einwahlkonferenzen ein. Dieser SIP-URI wird an verschiedenen Speicherorten angezeigt, einschließlich, aber nicht beschränkt auf Anrufbenachrichtigungen und frühere Versionen von Lync-Clients.
    
     > [!NOTE]
     > Der gleiche SIP-URI kann nicht von einer anderen Zugriffsnummer für Einwahlkonferenzen wiederverwendet werden. Der SIP-URI kann nach dem Erstellen der Zugriffsnummer nicht mehr geändert werden. Die einzige Möglichkeit, den SIP-URI zu ändern, ist das Löschen und Neu erstellen der Zugriffsnummer. 
  
   - Klicken Sie im Dropdownlistenfeld auf die Domäne der Konferenztelefonanwendung, die diese Einwahlnummer unterstützt.
    
9. Klicken **Sie in Pool** auf den Pool, in dem die Instanz der Konferenz attendant ausgeführt wird, die diese Einwahlzugriffsnummer unterstützt.
    
    > [!NOTE]
    > Wenn Sie den Pool ändern müssen, nachdem Sie die Zugriffsnummer erstellt haben, müssen Sie das [Cmdlet Move-CsApplicationEndpoint](/powershell/module/skype/move-csapplicationendpoint?view=skype-ps) verwenden oder die Zugriffsnummer löschen und neu erstellen.
  
10. Klicken **Sie in primärer** Sprache auf die Sprache, in der Eingabeaufforderungen für diese Einwahlnummer abgespielt werden. 
    
    Die primäre Sprache ist die Sprache, die die Konferenz attendant zum Beantworten des Anrufs verwendet. Unterstützte Sprachen werden zusammen mit jeder Zugriffstelefonnummer auf der Webseite "Einstellungen für Einwahlkonferenzen" angezeigt.
    
11. (Optional) Klicken Sie in sekundären **Sprachen (maximal vier)** auf **Hinzufügen,** wählen Sie eine oder mehrere zusätzliche Sprachen aus, die Sie für Anrufer dieser Einwahlnummer unterstützen möchten, und klicken Sie dann auf **OK**. 
    
    Sie können bis zu vier sekundäre Sprachen für jede Einwahlzugriffsnummer auswählen. Benutzer können eine sekundäre Sprache auswählen, bevor sie die Konferenz-ID eingeben, wenn sie sich bei einer Konferenz einwählen.
    
12. Klicken Sie zum Hinzufügen einer Region für die Einwahlnummer unter Zugeordnete Regionen auf **Hinzufügen**, klicken Sie auf eine oder mehrere Regionen, die den Wählplänen für diese Einwahlnummer zugeordnet sind, und klicken Sie dann auf **OK**.
    
13. Klicken Sie zum Löschen einer Region aus der Einwahlnummer unter Zugeordnete Regionen auf die Region, die Sie löschen möchten, und klicken Sie dann auf **Entfernen**.
    
14. Klicken Sie auf **Commit ausführen**.
    
## <a name="configure-conferencing-policies"></a>Konfigurieren von Konferenzrichtlinien
<a name="BKMK_ConfigureConferencingPolicies"> </a>

Die Konferenzrichtlinie ist eine Benutzerkontoeinstellung, die die Konferenzmöglichkeiten für Teilnehmer festlegt. Sie können Konferenzrichtlinien auf Standort- oder Benutzerebene erstellen. Konferenzrichtlinieneinstellungen umfassen viele Aspekte der Konferenzplanung und -teilnahme. Mehrere Konferenzrichtlinieneinstellungen unterstützen Einwahlkonferenzen für Teilnehmer. Bei der Konfiguration von Einwahlkonferenzen sollten Sie sicherstellen, dass diese Felder für Ihre Organisation angemessen festgelegt sind, und sie bei Bedarf bearbeiten. 
  
Weitere Informationen zum Konfigurieren von Konferenzrichtlinien finden Sie unter Verwalten von Konferenzrichtlinien [in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).
  
## <a name="assign-a-line-uri-to-a-user-account"></a>Zuweisen eines Zeilen-URI zu einem Benutzerkonto
<a name="BKMK_AssignaLineURI"> </a>

Teilnehmer an Einwahlkonferenzen geben ihre Telefonnummer oder Durchwahl sowie eine PIN ein, um als authentifizierte Benutzer an Konferenzen teilzunehmen. Der in Skype for Business Server-Benutzerkonten angegebene **Telefonieleitungs-URI** ist für die Authentifizierung erforderlich.
  
In diesem Thema wird beschrieben, wie Sie einem einzelnen Benutzerkonto einen **Anschluss-URI** zuweisen. Wenn Sie mehreren Benutzerkonten einen **Anschluss-URI** zuweisen möchten, können Sie ein Skript erstellen, das das Cmdlet **Set-CsUser** verwendet. Weitere Informationen zur Verwendung eines Beispielskripts zum Zuweisen von **Zeilen-URI** zu mehreren Benutzerkonten finden Sie unter [Assign Line URIs to Multiple Users](https://go.microsoft.com/fwlink/p/?linkId=196945).
  
1. Melden Sie sich beim Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle **Cs-UserAdministrator** oder **CsAdministrator** an.
    
2.  Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **Benutzer**.
    
4. Geben Sie in das Suchfeld den Namen des Benutzers ein, den Sie für Einwahlkonferenzen konfigurieren möchten, oder klicken Sie auf **Filter hinzufügen**, um Suchfelder anzugeben, und klicken Sie dann auf **Suchen**.
    
5. Doppelklicken Sie auf den Benutzernamen, um das Dialogfeld **Skype for Business Server-Benutzer** bearbeiten zu öffnen.
    
6. Geben Sie unter **Telefonie** in das Feld **Anschluss-URI** eine eindeutige, normalisierte Telefonnumer ein (beispielsweise tel:+14255550200).
    
    > [!NOTE]
    > Sie können den **Leitungs-URI** nur angeben, wenn **Telefonie** nur auf **PC-zu-PC,** Enterprise-VoIP **,** **Remoteanrufsteuerung** oder **Remoteanrufsteuerung festgelegt ist.** 
  
7. Klicken Sie auf **Commit ausführen**.
