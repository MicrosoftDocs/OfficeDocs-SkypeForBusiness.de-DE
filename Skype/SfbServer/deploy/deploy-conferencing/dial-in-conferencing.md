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
description: 'Zusammenfassung: Lesen Sie dieses Thema, um zu erfahren, wie Sie Einwahlkonferenzen in Skype for Business Server konfigurieren.'
ms.openlocfilehash: 5e6540b926d3b632fdff21f8fb645667068ca2e362260131dcd2b6379d5ef0b4
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54303129"
---
# <a name="configure-dial-in-conferencing-in-skype-for-business-server"></a>Konfigurieren von Einwahlkonferenzen in Skype for Business Server
 
**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie Einwahlkonferenzen in Skype for Business Server konfigurieren.
  
Nachdem Sie eine Topologie erstellt haben, die die Konferenzarbeitsauslastung und ausgewählte Einwahlkonferenzen enthält, müssen Sie zusätzliche Schritte zum Konfigurieren von Einwahlkonferenzen ausführen. Bevor Sie dieses Thema lesen, stellen Sie sicher, dass Sie den [Plan für Einwahlkonferenzen in Skype for Business Server,](../../plan-your-deployment/conferencing/dial-in-conferencing.md) [die Hardware- und Softwareanforderungen für Konferenzen in Skype for Business Server](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md)sowie das [Bereitstellungsflussdiagramm und die Prüfliste für Einwahlkonferenzen](deploy-conferencing.md#deployment-flowchart-and-checklist-for-dial-in-conferencing)gelesen haben. 
  
Zum Konfigurieren von Einwahlkonferenzen müssen Sie die folgenden Aufgaben ausführen:
  
- [Konfigurieren von Wähleinstellungen](dial-in-conferencing.md#BKMK_ConfigureDialPlans)
    
- [Konfigurieren von Regionen für Einwahlkonferenzen](dial-in-conferencing.md#BKMK_ConfigureDialInRegions)
    
- [Konfigurieren von Zugriffsnummern für die Einwahl](dial-in-conferencing.md#BKMK_ConfigureDialInAccessNumbers)
    
- [Konfigurieren von Konferenzrichtlinien](dial-in-conferencing.md#BKMK_ConfigureConferencingPolicies)
    
- [Zuweisen eines Anschluss-URI zu einem Benutzerkonto](dial-in-conferencing.md#BKMK_AssignaLineURI)
    
Darüber hinaus können Sie die folgenden optionalen Aufgaben ausführen. Weitere Informationen zu diesen optionalen Aufgaben finden Sie unter [Verwalten von Einwahlkonferenzen in Skype for Business Server.](../../manage/conferencing/dial-in-conferencing.md)
  
- Verwalten von PIN-Richtlinien für Einwahlkonferenzen
    
- Verwalten der Tastenzuordnung für DTMF-Befehle
    
- Erstellen von Konferenzverzeichnissen
    
- Verwalten von Ankündigungen für den Konferenzbeitritt und -verlassen
    
- Testen der Einwahlkonferenzeinstellungen
    
- Senden von Willkommens-E-Mails an Einwahlbenutzer
    
## <a name="configure-dial-plans"></a>Konfigurieren von Wähleinstellungen
<a name="BKMK_ConfigureDialPlans"> </a>

Bei der Bereitstellung von Einwahlkonferenzen müssen Sie einen oder mehrere Sätze mit Wähleinstellungen zum Routen von Zugriffsnummern für die Einwahl erstellen oder ändern. Sie müssen außerdem sicherstellen, dass jeder Wählplan mindestens eine Normalisierungsregel enthält – eine Regel, die Telefonerweiterungen in vollständige Telefonnummern im E.164-Format konvertiert. 
  
Benutzer von Einwahlkonferenzen nehmen an Konferenzen als authentifizierte Unternehmensbenutzer teil, indem sie ihre PIN und die Telefonnummer eingeben. Sie benötigen eine Normalisierungsregel zum Konvertieren von Durchwahlen in vollständige Rufnummern, damit Benutzer bei Eingabe einer Durchwahl authentifiziert werden können.
  
So richten Sie Wählpläne für Einwahlkonferenzen ein:
  
- Unabhängig davon, ob Sie Enterprise-VoIP bereitstellen oder nicht, ändern Sie den globalen Wählplan, um eine Region für Einwahlkonferenzen hinzuzufügen, und stellen Sie sicher, dass ihre Einwahlnummern durch eine Normalisierungsregel korrekt konvertiert werden. Ausführliche Anweisungen finden Sie unter [Erstellen oder Ändern eines Wählplans in Skype for Business Server.](../../deploy/deploy-enterprise-voice/dial-plans.md)
    
- Wenn Sie Enterprise-VoIP nicht bereitgestellt haben, erstellen Sie Wählpläne für Ihre Zugriffsnummern für Einwahlkonferenzen. Stellen Sie sicher, dass Sie eine Region für Einwahlkonferenzen angeben. Ausführliche Anweisungen finden Sie unter [Erstellen oder Ändern eines Wählplans in Skype for Business Server.](../../deploy/deploy-enterprise-voice/dial-plans.md)
    
- Wenn Sie Enterprise-VoIP bereitgestellt haben, ändern Sie nach Bedarf Enterprise-VoIP Wählpläne, um Regionen einzuschließen und geeignete Normalisierungsregeln für Einwahlnummern zu verwenden. Sie können auch dedizierte Wähleinstellungen erstellen, die nur für Zugriffsnummern für die Einwahl eingesetzt werden. Ausführliche Anweisungen finden Sie unter [Erstellen oder Ändern eines Wählplans in Skype for Business Server.](../../deploy/deploy-enterprise-voice/dial-plans.md)
    
Ausführliche Informationen zum Erstellen von Normalisierungsregeln finden Sie unter [Erstellen oder Ändern einer Normalisierungsregel in Skype for Business](../../deploy/deploy-enterprise-voice/normalization-rules.md).
  
## <a name="configure-dial-in-conferencing-regions"></a>Konfigurieren von Regionen für Einwahlkonferenzen
<a name="BKMK_ConfigureDialInRegions"> </a>

Wenn Sie einen Satz mit Wähleinstellungen einrichten, geben Sie die Region für Einwahlkonferenzen an, die für diese Wähleinstellungen gilt. Die Region für Einwahlkonferenzen ordnet Zugriffsnummern für Einwahlkonferenzen dem entsprechenden Wählplan zu. Wenn Sie anschließend die Zugriffsnummern für Einwahlkonferenzen erstellen, wählen Sie die Regionen aus, welche die Zugriffsnummern den geeigneten Wähleinstellungen zuordnen. 
  
Da es wichtig ist, eine Region für alle Wählpläne anzugeben, sollten Sie überprüfen, ob alle Wählpläne Konferenzregionen haben. 
  
Verwenden Sie das Cmdlet **"Get-CsDialPlan",** um zu überprüfen, ob die Region für alle Wählpläne für Einwahlkonferenzen festgelegt ist. Wenn die Region in einem Satz mit Wähleinstellungen fehlt, können Sie die Region mit dem Cmdlet **Set-CsDialPlan** festlegen. Sie können auch Skype for Business Server Systemsteuerung verwenden, um die Region in vorhandenen Wählplänen zu aktualisieren. Ausführliche Informationen zur Verwendung Skype for Business Server Systemsteuerung finden Sie unter [Erstellen oder Ändern eines Wählplans in Skype for Business Server.](../../deploy/deploy-enterprise-voice/dial-plans.md)
  
### <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a>So überprüfen Sie, ob für Wähleinstellungen die Region festgelegt wurde

1. Melden Sie sich beim Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** oder **CsAdministrator** an.
    
2. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start",** **"Alle Programme",** **"Skype for Business 2015"** und dann auf **Skype for Business Server Verwaltungsshell.**
    
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
    
2. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start",** **"Alle Programme",** **"Skype for Business 2015"** und dann auf **Skype for Business Server Verwaltungsshell.**
    
3. Führen Sie für alle Wähleinstellungen, in denen die Region für Einwahlkonferenzen fehlt, den folgenden Befehl aus:
    
   ```powershell
   Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
   ```

   Beispiel:
    
   ```powershell
   Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
   ```

   In diesem Beispiel wird die Eigenschaft "DialinConferencingRegion" in den Wähleinstellungen mit der Identität "Redmond" in den Wert "US West Coast" geändert. 
    
Weitere Informationen finden Sie unter ["Set-CsDialPlan".](/powershell/module/skype/set-csdialplan?view=skype-ps)
  
## <a name="configure-dial-in-access-numbers"></a>Konfigurieren von Zugriffsnummern für die Einwahl
<a name="BKMK_ConfigureDialInAccessNumbers"> </a>

Beim Bereitstellen von Einwahlkonferenzen müssen Sie Telefonnummern einrichten, die Benutzer aus dem Telefonfestnetz (Public Switched Telephone Network, PSTN) wählen können, um am Audioteil einer Konferenz teilzunehmen. Diese Zugriffsnummern für die Einwahl werden in Besprechungseinladungen und auf der Webseite mit den Einstellungen für Einwahlkonferenzen angezeigt.
  
Vor dem Erstellen von Zugriffsnummern für die Einwahl müssen Sie zunächst die Regionen Ihrer Einwahlkonferenzen planen und anschließend Wählpläne für die Regionen konfigurieren. Ausführliche Informationen zu Regionen finden Sie unter [Plan for dial-in conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md). Ausführliche Informationen zum Konfigurieren von Wählplänen für Einwahlkonferenzen finden Sie unter [Erstellen oder Ändern eines Wählplans in Skype for Business Server.](../../deploy/deploy-enterprise-voice/dial-plans.md)
  
> [!NOTE]
> Sie können eine neue Zugriffsnummer erst dann für Einwahlkonferenzen verwenden, wenn die Replikation der Active Directory-Domänendienste (AD DS) für diese Zugriffsnummer abgeschlossen ist. Die Replikation kann mehrere Stunden in Anspruch nehmen. 
  
> [!NOTE]
> Nach dem Erstellen von Zugriffsnummern für die Einwahl können Sie den Anzeigenamen für die Active Directory-Kontaktobjekte modifizieren, sodass Benutzer die richtige Zugriffsnummer einfacher identifizieren können. Verwenden Sie zum Ändern des Anzeigenamens das Cmdlet ["Set-CsDialInConferencingAccessNumber".](/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) Active Directory-Objekte sollten nicht manuell geändert werden.
  
### <a name="to-create-a-dial-in-access-number"></a>So erstellen Sie eine Einwahlnummer

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Öffnen Sie Skype for Business Server Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **Konferenz** und dann auf **Zugriffsnummer für Einwahl**.
    
4. Führen Sie auf der Seite **"Einwahlzugriffsnummer"** eine der folgenden Aktionen aus:
    
   - Klicken Sie auf **Neu,** um **die neue Einwahlnummer** zu öffnen.
    
   - Klicken Sie auf eine der Einwahlnummern in der Liste, klicken Sie auf **"Bearbeiten"** und dann auf **"Details anzeigen".**
    
     > [!NOTE]
     > Die Verwendung des Suchfelds zum Suchen nach dem Inhalt einer Spalte in der Liste der Einwahlnummern liefert möglicherweise nicht die erwarteten Ergebnisse. Sortieren Sie stattdessen die Liste nach der gewünschten Spalte, um die Einwahlnummer zu identifizieren, die Sie anzeigen oder ändern möchten. 
  
5. Geben Sie in der **Anzeigenummer** die Telefonnummer ein, die PSTN-Telefonbenutzer wählen, um an einer Konferenz teilzunehmen. Diese Nummer wird in Besprechungseinladungen und auf der Webseite für Einwahlkonferenzen Einstellungen angezeigt.
    
6. Geben Sie unter **Anzeigename** eine Beschreibung für die Zugriffsnummer für die Einwahl ein. Dies ist der Name, der der Einwahlzugriffsnummer in Skype for Business Suchergebnissen zugeordnet ist. Dieser Name wird im Client angezeigt, wenn ein Benutzer die Zugriffsnummer aufruft. 
    
7. Geben Sie im **Anschluss-URI** die E.164-Nummer der Einwahlnummer im TEL-URI-Format ein, einschließlich des +-Symbols vor der Nummer und ohne Leerzeichen. Beispiel: tel:+14255550200.
    
    > [!NOTE]
    > Derselbe Anschluss-URI kann nicht von einer anderen Zugriffsnummer für Einwahlkonferenzen wiederverwendet werden. 
  
8. Führen **Sie im SIP-URI** die folgenden Schritte aus:
    
   - Geben Sie im Textfeld einen eindeutigen SIP-URI für diese Zugriffsnummer für Einwahlkonferenzen ein. Dieser SIP-URI wird an verschiedenen Speicherorten angezeigt, einschließlich, aber nicht beschränkt auf, Anrufbenachrichtigungen und frühere Versionen von Lync-Clients.
    
     > [!NOTE]
     > Derselbe SIP-URI kann nicht von einer anderen Zugriffsnummer für Einwahlkonferenzen wiederverwendet werden. Der SIP-URI kann nicht geändert werden, nachdem die Zugriffsnummer erstellt wurde. Die einzige Möglichkeit zum Ändern des SIP-URI besteht darin, die Zugriffsnummer zu löschen und neu zu erstellen. 
  
   - Klicken Sie im Dropdownlistenfeld auf die Domäne des Konferenzzentralenanwendung, das diese Einwahlnummer unterstützt.
    
9. Klicken Sie im **Pool** auf den Pool, in dem die Instanz von Konferenzzentrale ausgeführt wird, die diese Einwahlnummer unterstützt.
    
    > [!NOTE]
    > Wenn Sie den Pool ändern müssen, nachdem Sie die Zugriffsnummer erstellt haben, müssen Sie das Cmdlet ["Move-CsApplicationEndpoint"](/powershell/module/skype/move-csapplicationendpoint?view=skype-ps) verwenden oder die Zugriffsnummer löschen und neu erstellen.
  
10. Klicken Sie in der **Primären Sprache** auf die Sprache, in der Eingabeaufforderungen für diese Einwahlnummer wiedergegeben werden. 
    
    Die primäre Sprache ist die Sprache, die der Konferenzzentrale verwendet, um den Anruf zu beantworten. Unterstützte Sprachen werden zusammen mit jeder Zugriffstelefonnummer auf der Webseite für Einwahlkonferenzen Einstellungen angezeigt.
    
11. (Optional) Klicken Sie in **sekundären Sprachen (maximal vier)** auf **"Hinzufügen",** wählen Sie eine oder mehrere zusätzliche Sprachen aus, die Sie für Anrufer für diese Einwahlnummer unterstützen möchten, und klicken Sie dann auf **"OK".** 
    
    Sie können für jede Einwahlnummer bis zu vier sekundäre Sprachen auswählen. Benutzer können eine sekundäre Sprache auswählen, bevor sie die Konferenz-ID eingeben, wenn sie sich in eine Konferenz einwählen.
    
12. Klicken Sie zum Hinzufügen einer Region für die Zugriffsnummer für die Einwahl unter **"Zugeordnete Regionen"** auf **"Hinzufügen",** klicken Sie auf eine oder mehrere Regionen, die den Wählplänen für diese Einwahlnummer zugeordnet sind, und klicken Sie dann auf **"OK".**
    
13. Um eine Region aus der Einwahlnummer zu löschen, klicken Sie unter **"Zugeordnete Regionen"** auf die Region, die Sie löschen möchten, und klicken Sie dann auf **"Entfernen".**
    
14. Klicken Sie auf **Commit ausführen**.
    
## <a name="configure-conferencing-policies"></a>Konfigurieren von Konferenzrichtlinien
<a name="BKMK_ConfigureConferencingPolicies"> </a>

Die Konferenzrichtlinie ist eine Benutzerkontoeinstellung, die die Konferenzmöglichkeiten für Teilnehmer festlegt. Sie können Konferenzrichtlinien auf Standort- oder Benutzerebene erstellen. Konferenzrichtlinieneinstellungen umfassen viele Aspekte der Konferenzplanung und -teilnahme. Mehrere Konferenzrichtlinieneinstellungen unterstützen Einwahlkonferenzen für Teilnehmer. Bei der Konfiguration von Einwahlkonferenzen sollten Sie sicherstellen, dass diese Felder für Ihre Organisation angemessen festgelegt sind, und sie bei Bedarf bearbeiten. 
  
Weitere Informationen zum Konfigurieren von Konferenzrichtlinien finden Sie unter [Verwalten von Konferenzrichtlinien in Skype for Business Server.](../../manage/conferencing/conferencing-policies.md)
  
## <a name="assign-a-line-uri-to-a-user-account"></a>Zuweisen eines Anschluss-URI zu einem Benutzerkonto
<a name="BKMK_AssignaLineURI"> </a>

Teilnehmer an Einwahlkonferenzen geben ihre Telefonnummer oder Durchwahl sowie eine PIN ein, um als authentifizierte Benutzer an Konferenzen teilzunehmen. Der für Skype for Business Server Benutzerkonten angegebene **Telefonieleitungs-URI** ist für die Authentifizierung erforderlich.
  
In diesem Thema wird beschrieben, wie Sie einem einzelnen Benutzerkonto einen **Anschluss-URI** zuweisen. Wenn Sie mehreren Benutzerkonten einen **Anschluss-URI** zuweisen möchten, können Sie ein Skript erstellen, das das Cmdlet **Set-CsUser** verwendet. Ausführliche Informationen zur Verwendung eines Beispielskripts zum Zuweisen von **Zeilen-URI** zu mehreren Benutzerkonten finden Sie unter [Zuweisen von Zeilen-URIs zu mehreren Benutzern.](https://go.microsoft.com/fwlink/p/?linkId=196945)
  
1. Melden Sie sich beim Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle **Cs-UserAdministrator** oder **CsAdministrator** an.
    
2.  Öffnen Sie Skype for Business Server Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **Benutzer**.
    
4. Geben Sie in das Suchfeld den Namen des Benutzers ein, den Sie für Einwahlkonferenzen konfigurieren möchten, oder klicken Sie auf **Filter hinzufügen**, um Suchfelder anzugeben, und klicken Sie dann auf **Suchen**.
    
5. Doppelklicken Sie auf den Benutzernamen, um das Dialogfeld **Skype for Business Server Benutzer** bearbeiten zu öffnen.
    
6. Geben Sie unter **Telefonie** in das Feld **Anschluss-URI** eine eindeutige, normalisierte Telefonnumer ein (beispielsweise tel:+14255550200).
    
    > [!NOTE]
    > Sie können **den Anschluss-URI** nur angeben, wenn die **Telefonie** nur auf **PC zu PC** festgelegt ist, nur **Enterprise-VoIP,** **Remoteanrufsteuerung** oder **Remoteanrufsteuerung.** 
  
7. Klicken Sie auf **Commit ausführen**.
