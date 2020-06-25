---
title: Verwalten von Ressourcenkonten in Teams
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: jastark, wasseemh
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
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
- seo-marvel-apr2020
description: In diesem Artikel erfahren Sie, wie Sie Ressourcenkonten in Microsoft Teams erstellen, bearbeiten und verwalten können.
ms.openlocfilehash: b47e00323129211f657ec1dafc4e62a7cd6e4321
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2020
ms.locfileid: "44868612"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>Verwalten von Ressourcenkonten in Microsoft Teams

Ein Ressourcenkonto wird in Azure AD auch als *deaktiviertes Benutzerobjekt* bezeichnet und kann verwendet werden, um Ressourcen allgemein darzustellen. In Exchange kann es z. B. verwendet werden, um Konferenzräume darzustellen und ermöglicht, dass diese eine Telefonnummer haben. Ein Ressourcenkonto kann in Microsoft 365 oder lokal unter Verwendung von Skype for Business Server 2019 verwaltet werden.

In Microsoft Teams oder Skype for Business Online ist für jede Telefonsystem-Anrufwarteschleife oder automatische Telefonzentrale mindestens ein zugeordnetes Ressourcenkonto erforderlich. Ob ein Ressourcenkonto eine zugewiesene Telefonnummer benötigt, hängt von der vorgesehenen Verwendung der zugehörigen Anrufwarteschleife oder der automatischen Telefonzentrale ab, wie im folgenden Diagramm dargestellt. Sie können auch die Artikel zu Anrufwarteschleifen und automatischen Telefonzentralen, die am Ende dieses Artikels verknüpft sind, zu Rate ziehen, bevor Sie einem Ressourcenkonto eine Telefonnummer zuweisen.

![Beispiel für Ressourcenkonten und Benutzerlizenzen](media/resource-account.png)

> [!NOTE]
> Dieser Artikel bezieht sich auf Microsoft Teams und Skype for Business Online. Informationen zu Ressourcenkonten, die in Skype for Business Server 2019 verwaltet werden, finden Sie unter [Konfigurieren von Ressourcenkonten](/SkypeForBusiness/hybrid/configure-onprem-ra).

## <a name="assign-a-phone-number-to-a-phone-system-call-queue"></a>Zuweisen einer Telefonnummer zu einer Telefon System-Anrufwarteschlange

Wenn Ihre Organisation bereits mindestens eine Telefonsystemlizenz verwendet, können Sie einer Telefonsystem-Anrufwarteschleife wie folgt eine Telefonnummer zuweisen:

1. Rufen sie eine Dienstnummer ab.
2. Rufen Sie eine kostenlose Telefonsystem – [virtuelle Benutzerlizenz](teams-add-on-licensing/virtual-user.md) oder eine kostenpflichtige Telefonsystemlizenz ab, die mit dem Ressourcenkonto oder einer Telefonsystemlizenz verwendet werden soll.
3. Erstellen Sie das Ressourcenkonto. Eine automatische Telefonzentrale oder Anrufwarteschleife muss über ein zugeordnetes Ressourcenkonto verfügen.
4. Weisen Sie dem Ressourcenkonto das Telefonsystem oder eine Telefonsystem – virtuelle Benutzerlizenz zu.
5. Weisen Sie dem Ressourcenkonto, dem Sie gerade Lizenzen zugewiesen haben, eine Dienstelefonnummer zu.
6. Erstellen einer Warteschlange oder eine automatische Telefonzentrale für das Telefonsystem
7. Verknüpfen Sie das Ressourcenkonto mit einer Anrufwarteschleife oder einer automatischen Telefonzentrale.

<!-- Auto attendants created after November 1st, 2019 also create a new resource account that is associated with the auto attendant. If a phone number is applied to the auto attendant's resource account,  a Phone System - Virtual user license is applied to the resource account if one is available. -->

Wenn die automatische Telefonzentrale oder die Anrufwarteschlange unter einer automatischen Telefonzentrale der obersten Ebene geschachtelt ist, benötigt das zugeordnete Ressourcenkonto nur eine Telefonnummer, wenn Sie mehrere Einstiegspunkte in die Struktur von automatischen Telefonzentralen und Anrufwarteschlangen einbeziehen möchten.

Zum Umleiten von Anrufen an Personen in Ihrer Organisation, die Online verwaltet werden, müssen Sie über eine **Telefon System** Lizenz verfügen und für Enterprise-VoIP aktiviert sein oder über Microsoft 365 oder Office 365-Anrufpläne verfügen. Weitere Informationen finden Sie unter [Zuweisen von Microsoft Teams-Add-on-Lizenzen](teams-add-on-licensing/assign-teams-add-on-licenses.md). Wenn Sie sie für Enterprise-VoIP aktivieren möchten, können Sie Windows PowerShell verwenden. Führen Sie beispielsweise den folgenden Befehl aus: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

> [!WARNING]
> Um Probleme mit dem Ressourcenkonto zu vermeiden, führen Sie die folgenden Schritte in dieser Reihenfolge aus.

Wenn die von Ihnen erstellte Telefonsystem-Anrufwarteschleife oder Telefonzentrale geschachtelt wird und keine Telefonnummer benötigt, ist die Vorgehensweise:

1. Erstellen des Ressourcenkontos
2. Erstellen einer Warteschlange oder eine automatische Telefonzentrale für das Telefonsystem
3. Verknüpfen des Ressourcenkontos mit einer Anrufwarteschleife oder einer automatischen Telefonzentrale

### <a name="create-a-resource-account-with-a-phone-number"></a>Erstellen eines Ressourcenkontos mit einer Telefonnummer

<a name="phonenumber"> </a>

> [!IMPORTANT]
> Eine Telefonnummer wird nicht direkt der automatischen Telefonzentrale oder Anrufwarteschlange, sondern dem Ressourcenkonto zugewiesen, das der automatischen Telefonzentrale oder Anrufwarteschlange zugeordnet ist.

Eine automatische Telefonzentrale oder Anrufwarteschleife der obersten Ebene erfordert, dass eine Telefonnummer mit ihrer automatischen Telefonzentrale verknüpft wird. Wenn Sie ein Ressourcenkonto erstellen möchten, das eine Telefonnummer verwendet, ist die Vorgehensweise:

1. Portieren Sie eine gebührenpflichtige oder gebührenfreie Dienstnummer oder rufen Sie diese ab. Die Nummer kann keiner anderen Voice Services oder Ressourcenkonten zugewiesen werden.

   Bevor Sie einem Ressourcenkonto eine Telefonnummer zuweisen, müssen Sie Ihre bestehenden gebührenpflichtigen oder gebührenfreien Dienstnummern abrufen oder portieren. Nachdem Sie die gebührenpflichtigen oder gebührenfreien Diensttelefonnummern erhalten haben, werden diese unter **Microsoft Teams Admin Center** > **Voice** > **Telefonnummern** angezeigt, und der **Nummerntyp** wird als **Dienst – gebührenfrei** aufgelistet. Informationen zum Abrufen Ihrer Dienstnummern finden Sie unter [Abrufen von Service-Telefonnummern](getting-service-phone-numbers.md) oder wenn Sie eine vorhandene Service-Nummer übertragen möchten, finden Sie unter [übertragen von Telefonnummern in Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).

   Wenn Sie einem Ressourcenkonto eine Telefonnummer zuweisen, können Sie jetzt die ﻿kostenlose virtuelle Benutzerlizenz des Telefonsystems verwenden. Auf diese Weise können Telefonsystem-Funktionen für Telefonnummern auf Organisationsebene bereitgestellt werden, und Sie können die Funktionen der automatischen Telefonzentrale und der Anrufwarteschleife erstellen.

2. Rufen Sie eine virtuelle Benutzerlizenz für das Telefonsystem oder eine herkömmliche Telefonsystemlizenz ab.

   Wenn Sie die Lizenz für virtuelle Benutzer erhalten möchten, wechseln Sie im Microsoft 365 Admin Center zu den Abonnements für **Billing**  >  **Purchase Services**-  >  **Add-on** , und Scrollen Sie bis zum Ende – Sie sehen die Lizenz "Telefon System-virtueller Benutzer". Wählen Sie **Jetzt kaufen** aus. Es entstehen keine Kosten, Sie müssen jedoch dennoch die diese Schritte befolgen, um die Lizenz zu erwerben.
3. Erstellen Sie ein neues Ressourcenkonto. Informationen finden Sie unter [Erstellen eines Ressourcenkontos im Microsoft Teams Admin Center](#create-a-resource-account-in-the-microsoft-teams-admin-center) oder [Erstellen eines Ressourcenkontos in PowerShell](#create-a-resource-account-in-powershell).
4. Weisen Sie dem Ressourcenkonto eine Telefonsystem – [virtuelle Benutzerlizenz](teams-add-on-licensing/virtual-user.md) oder eine Telefonsystemlizenz zu. Weitere Informationen finden Sie unter [Zuweisen von Microsoft Teams-Add-on-Lizenzen](teams-add-on-licensing/assign-teams-add-on-licenses.md) und [Zuweisen von Lizenzen zu Benutzern](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).
5. Weisen Sie dem Ressourcenkonto die Dienstnummer zu. Informationen finden Sie unter [Zuweisen oder aufheben der Zuweisung von Telefonnummern und Diensten](#assignunassign-phone-numbers-and-services).
6. Richten Sie eines der Folgenden ein:
   - [Automatische Cloud-Telefonzentrale](create-a-phone-system-auto-attendant.md)
   - [Cloud-Anrufwarteschleife](create-a-phone-system-call-queue.md)
7. Verknüpfen Sie das Ressourcenkonto mit der automatischen Telefonzentrale oder der Anrufwarteschleife. Informationen finden Sie unter [Zuweisen oder aufheben der Zuweisung von Telefonnummern und Diensten](#assignunassign-phone-numbers-and-services).

Wenn Sie beim Erstellen einer automatischen Telefonzentrale ein Ressourcenkonto erstellen, werden die Lizenzen automatisch zugewiesen.

### <a name="create-a-resource-account-without-a-phone-number"></a>Erstellen eines Ressourcenkontos ohne Telefonnummer

Eine geschachtelte automatische Telefonzentrale oder Anrufwarteschleife erfordert ein Ressourcenkonto, aber in vielen Fällen benötigt das entsprechende Ressourcenkonto keine Telefonnummer und die erforderliche Lizenzierung, um eine Telefonnummer zu unterstützen. Wenn Sie ein Ressourcenkonto erstellen, für das keine Rufnummer erforderlich ist, müssen Sie die folgenden Aufgaben in der folgenden Reihenfolge ausführen:

1. Erstellen Sie ein neues Ressourcenkonto. Informationen finden Sie unter [Erstellen eines Ressourcenkontos in Microsoft Teams Admin Center](#create-a-resource-account-in-the-microsoft-teams-admin-center) oder [Erstellen eines Ressourcenkontos in PowerShell](#create-a-resource-account-in-powershell).

2. Richten Sie eines der Folgenden ein:
   - [Automatische Cloud-Telefonzentrale](create-a-phone-system-auto-attendant.md)
   - [Cloud-Anrufwarteschleife](create-a-phone-system-call-queue.md)
   
3. Weisen Sie das Ressourcenkonto der Anrufwarteschleife oder der automatischen Telefonzentrale zu. Informationen finden Sie unter [Zuweisen oder aufheben der Zuweisung von Telefonnummern und Diensten](#assignunassign-phone-numbers-and-services).


## <a name="create-a-resource-account-in-the-microsoft-teams-admin-center"></a>Erstellen eines Ressourcenkontos im Microsoft Teams Admin Center

Nachdem Sie eine Telefon System Lizenz gekauft haben, wechseln Sie in der linken Navigationsleiste des Microsoft Teams admin Centers zu **organisationsweiten Einstellungen-**  >  **Ressourcenkonten**.

![Screenshot der Seite „Ressourcenkonten“](media/r-a-master.png)

![Symbol der Zahl 1, das auf eine Legende im vorherigen Screenshot verweist](media/teamscallout1.png)

Klicken Sie auf **Hinzufügen**, um ein neues Ressourcenkonto zu erstellen. Füllen Sie im Bereich **Ressourcenkonto hinzufügen** den **Anzeige Namen**, den **Benutzernamen** aus (der Domänenname sollte automatisch aufgefüllt werden), und geben Sie den **Ressourcen Kontotyp** für das Ressourcenkonto ein. Der Typ des Ressourcenkontos kann eine **automatische Telefonzentrale** oder eine **Anrufwarteschlange**sein, abhängig von der APP, die Sie dem Ressourcenkonto zuordnen möchten. Wenn Sie fertig sind, klicken Sie auf **Speichern**.

![Screenshot der Optionen für „Neues Ressourcenkonto“](media/res-acct.png)

Wenden Sie als nächstes eine Lizenz auf das Ressourcenkonto im Microsoft 365 Admin Center an, wie unter [Zuweisen von Lizenzen zu Benutzern](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)beschrieben.

### <a name="edit-resource-account"></a>Ressourcenkonto bearbeiten 

![Symbol der Zahl 2, die auf eine Legende im vorherigen Screenshot verweist ](media/teamscallout2.png) Sie können den **Anzeigenamen** des Ressourcenkontos und den **Ressourcen Kontotyp** mithilfe der Option " **Bearbeiten** " bearbeiten. Klicken Sie abschließend auf **Speichern**.

![Screenshot der Option „Ressourcenkonto bearbeiten“](media/r-a-edit.png)

<a name="phonenumber"> </a>

### <a name="assignunassign-phone-numbers-and-services"></a>Zuweisen/Aufheben der Zuweisung von Telefonnummern und Diensten

![Symbol der Zahl 3, die auf eine Legende im vorherigen Screenshot verweist ](media/teamscallout3.png) nachdem Sie das Ressourcenkonto erstellt und die Lizenz zugewiesen haben, können Sie auf zuweisen **/** Aufheben der Zuweisung klicken, um dem Ressourcenkonto eine Dienstnummer zuzuweisen, den Typ der Telefonnummer festzulegen oder das Ressourcenkonto einer bestimmten automatischen Telefonzentrale oder Anrufwarteschlange zuzuweisen, die bereits vorhanden ist. Das Zuweisen einer direkten Routingnummer kann nur über Cmdlets erfolgen. Wenn Sie die Anrufwarteschlange oder die automatische Telefonzentrale, die Sie dem Ressourcenkonto zuordnen, noch nicht erstellt haben, lassen Sie das Feld leer. Sie können das Ressourcenkonto während der Erstellung verknüpfen. Klicken Sie abschließend auf **Speichern**.

Die Optionen für den **Typ "Telefonnummer** " lauten wie folgt:

- Keine
- Online
- Gebührenfrei
- Lokal

![Screenshot der Optionen „Zuweisen/Aufheben der Zuweisung“](media/r-a-assign.png)

Wenn Sie einem Ressourcenkonto eine direkte Routing-oder Hybrid-Nummer zuweisen möchten, müssen Sie PowerShell verwenden, siehe hierzu den folgenden Abschnitt.

> [!IMPORTANT]
> Wenn Ihr Ressourcenkonto nicht über eine gültige Lizenz verfügt, führt eine interne Prüfung zu einem Fehler, wenn Sie versuchen, die Telefonnummer dem Ressourcenkonto zuzuweisen. Sie sind dann nicht in der Lage, die Nummer zuzuweisen oder das Ressourcenkonto einer Anrufwarteschleife oder automatischen Telefonzentrale zuzuordnen.

> [!IMPORTANT]
> Eine Telefonnummer wird nicht direkt der automatischen Telefonzentrale oder Anrufwarteschlange, sondern dem Ressourcenkonto zugewiesen, das der automatischen Telefonzentrale oder Anrufwarteschlange zugeordnet ist.



## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a>Ändern eines vorhandenen Ressourcenkontos, um eine virtuelle Benutzerlizenz zu verwenden

Wenn Sie sich entscheiden, die Lizenzen für Ihr vorhandenes Ressourcenkonto von einer Telefon System Lizenz zu einer virtuellen Benutzerlizenz zu wechseln, müssen Sie die ﻿kostenlose virtuelle Benutzerlizenz erwerben und dann die Schritte im Microsoft 365 Admin Center ausführen, um [Benutzer in ein anderes Abonnement zu verschieben](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).

> [!WARNING]
> Entfernen Sie immer die vollständige Telefonsystemlizenz und weisen Sie die virtuelle Benutzerlizenz der gleichen Lizenzaktivität zu. Wenn Sie die alte Lizenz entfernen, die Kontoänderungen speichern, die neue Lizenz hinzufügen und dann die Kontoeinstellungen erneut speichern, funktioniert das Ressourcenkonto möglicherweise nicht mehr wie erwartet. In diesem Fall empfiehlt es sich, ein neues Ressourcenkonto für die virtuelle Benutzerlizenz zu erstellen und das beschädigte Ressourcenkonto zu entfernen.

## <a name="create-a-resource-account-in-powershell"></a>Erstellen eines Ressourcenkontos in PowerShell

Je nachdem, ob Ihr Ressourcenkonto online oder in Skype for Business 2019 vorliegt, müssen Sie eine Verbindung mit der entsprechenden PowerShell-Eingabeaufforderung mit Administratorrechten herstellen.

- In den folgenden Beispielen für PowerShell-Cmdlets wird gezeigt, wie Sie mit [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) ein online verwaltetes Ressourcenkonto erstellen. 

- Informationen zu Ressourcenkonten in Skype for Business Server 2019, die mit Cloud-Anrufwarteschlangen und automatischen Cloud-Telefonzentralen verwendet werden können, finden Sie unter [Planen von Cloud-Anrufwarteschlangen](/SkypeforBusiness/hybrid/plan-call-queue) oder [Planen automatischer Cloud-Telefonzentralen](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant). Hybrid Implementierungen (Zahlen, die im direkten Routing verwaltet werden) werden mithilfe des Cmdlets [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) auf einem lokalen Skype for Business Server 2019-Server konfiguriert.

Die Anwendungs-IDs, die Sie beim Erstellen der Anwendungsinstanzen benötigen, sind Folgende:

- **Automatische Telefonzentrale:** ce933385-9390-45d1-9512-c8d228074e07
- **Anrufwarteschleife:** 11cd3e2e-fccb-42ad-ad00-878b93575e07

> [!NOTE]
> Wenn Sie möchten, dass die Anrufwarteschleife oder automatische Telefonzentrale von Benutzern von Skype For Business Server 2019 durchsucht werden kann, sollten Sie Ihre Ressourcenkonten in Skype For Business Server 2019 erstellen, da Online-Ressourcenkonten nicht mit Active Directory synchronisiert werden. Wenn DNS-SRV-Einträge für sipfederationtls in Skype for Business Server 2019 aufgelöst werden, dann **müssen** die Ressourcenkonten mithilfe der SfB-Management-Shell in Skype for Business Server 2019 erstellt und mit Azure AD online synchronisiert werden.

 

1. Verwenden Sie den folgenden Befehl, um ein Ressourcenkonto für die Verwendung mit einer automatischen Telefonzentrale online zu erstellen:

    ``` Powershell
    New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId "ce933385-9390-45d1-9512-c8d228074e07" -DisplayName "Resource account 1"
    ```

2. Sie können das Ressourcenkonto erst dann verwenden, wenn Sie ihm eine Lizenz zuweisen. Informationen dazu, wie Sie eine Lizenz auf ein Konto im Microsoft 365 Admin Center anwenden, finden Sie unter[Zuweisen von Lizenzen zu Benutzern](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users) und [Zuweisen von Lizenzen für Skype for Business](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).

3. Optional Nachdem die richtige Lizenz auf das Ressourcenkonto angewendet wurde, können Sie dem Ressourcenkonto eine Telefonnummer zuweisen, wie unten dargestellt. Nicht alle Ressourcenkonten benötigen eine Telefonnummer. Wenn Sie keine Lizenz auf das Ressourcenkonto angewendet haben, schlägt die Zuweisung der Telefonnummer fehl.

   ``` Powershell
   Set-CsOnlineVoiceApplicationInstance -Identity testra1@contoso.com -TelephoneNumber +14255550100
   Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
   ```

   Weitere Details hierzu finden Sie unter [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps).

   > [!NOTE]
   > Die Online-Telefonnummer lässt sich am einfachsten mithilfe des Microsoft Teams Admin Centers festlegen, wie zuvor beschrieben.

   Wenn Sie einem (in Microsoft Teams oder Skype for Business Server 2019 verwalteten) Ressourcenkonto eine direkte Routingtelefonnummer zuweisen möchten, verwenden Sie das folgende Cmdlet für Skype for Business Online PowerShell:

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

## <a name="manage-resource-account-settings-in-the-microsoft-teams-admin-center"></a>Verwalten von Ressourcenkonto Einstellungen im Microsoft Teams Admin Center

Wenn Sie die Ressourcenkonto Einstellungen im Microsoft Teams Admin Center verwalten möchten, wechseln Sie zu **organisationsweiten Einstellungen**  >  **Ressourcenkonten**, wählen Sie das Ressourcenkonto aus, für das Sie die Einstellungen ändern müssen, und klicken Sie dann auf **Bearbeiten**. Im Bereich **Ressourcenkonto bearbeiten** können Sie die folgenden Einstellungen ändern:

- **Anzeigename** für das Konto
- Anrufwarteschleife oder automatische Telefonzentrale, die das Konto verwendet
- Dem Konto zugewiesene Telefonnummer

Klicken Sie abschließend auf **Speichern**.

## <a name="delete-a-resource-account"></a>Löschen eines Ressourcenkontos

Stellen Sie sicher, dass Sie die Telefonnummer vom Ressourcenkonto trennen, bevor Sie sie löschen, um zu verhindern, dass Ihre Dienstnummer im Modus „Ausstehend“ verbleibt. Dazu können Sie das folgende Cmdlet verwenden:

``` Powershell
Set-CsOnlineVoiceApplicationInstance -Identity <Resource Account oid> -TelephoneNumber $null
```

Anschließend können Sie das Ressourcenkonto im Microsoft 365 Admin Center auf der Registerkarte Benutzer löschen.

Verwenden Sie den folgenden Cmdlet, um eine direkte Routing-Telefonnummer vom Ressourcenkonto zu trennen:

``` Powershell
Set-CsOnlineApplicationInstance -Identity  <Resource Account oid> -OnpremPhoneNumber ""
```

## <a name="troubleshooting"></a>Problembehandlung

### <a name="you-dont-see-the-phone-number-assigned-to-the-resource-account-in-the-microsoft-teams-admin-center"></a>Im Microsoft Teams Admin Center wird die Telefonnummer, die dem Ressourcenkonto zugewiesen ist, nicht angezeigt.

Wenn die Telefonnummer, die dem Ressourcenkonto im Microsoft Teams Admin Center zugewiesen ist, nicht angezeigt wird und Sie die Nummer nicht von dort aus zuweisen können, überprüfen Sie Folgendes:

``` Powershell
Get-MsolUser -UserPrincipalName "username@contoso.com"| fl objectID,department
```

Wenn das Department-Attribut den Skype for Business-Anwendungsendpunkt anzeigt, führen Sie das folgende Cmdlet aus:

``` Powershell
Set-MsolUser -ObjectId -Department "Microsoft Communication Application Instance"
```

> [!NOTE]
> Aktualisieren Sie nach dem Ausführen des cmldet die Website des Teams Admin Centers. Sie sollten dann in der Lage sein, die Nummer ordnungsgemäß zuzuweisen.

### <a name="you-get-a-we-cant-use-this-resource-account-for-services-error-message"></a>Sie erhalten ein "Wir können dieses Ressourcenkonto nicht für Dienste verwenden". Fehlermeldung

<a name="blocksignin"> </a>

Wenn Sie versuchen, ein Ressourcenkonto zu verwenden, erhalten Sie die folgende Fehlermeldung:

"Dieses Ressourcenkonto kann nicht für Dienste verwendet werden. Das Ressourcenkonto muss deaktiviert und für die Anmeldung gesperrt sein. Sie müssen die Anmeldung für dieses Ressourcenkonto auf der Seite "Benutzer" im Microsoft 365 Admin Center blockieren. "

Wenn Sie ein Ressourcenkonto erstellen, ist es standardmäßig deaktiviert, und die Anmeldung ist für das Konto gesperrt. Diese Einstellungen sollten nicht geändert werden. Um diese Fehlermeldung zu beheben, blockieren Sie das Ressourcenkonto, bevor Sie sich anmelden. Gehen Sie dazu so vor:

1. Wechseln Sie im Microsoft 365 Admin Center zu **Benutzer**, suchen Sie nach, und wählen Sie dann das Ressourcenkonto aus.
2. Klicken Sie oben im Bereich unter dem Anzeigenamen auf **diesen Benutzer blockieren?**, aktivieren Sie das Kontrollkästchen **diesen Benutzer von der Anmeldung blockieren** , und wählen Sie dann **Änderungen speichern**aus.

   ![Screenshot der Option "diesen Nutzer blockieren"](media/res-acct-block.png)

    Anschließend wird unter dem Anzeigenamen "Anmelden blockiert" angezeigt.

      ![Screenshot der Meldung "Anmeldung blockiert"](media/res-acct-sign-in-blocked.png)

## <a name="related-information"></a>Verwandte Informationen

Bei hybride Implementierungen mit Skype for Business Server:

   [Planen automatischer Cloudtelefonzentralen](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [Planen von Cloud-Anrufwarteschleifen](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [Konfigurieren lokalen von Ressourcenkonten](/SkypeForBusiness/hybrid/configure-onprem-ra)


Bei Implementierungen in Teams oder Skype for Business Online:

   [Was sind automatische Cloudtelefonzentralen?](what-are-phone-system-auto-attendants.md)

   [Einrichten einer automatischen Cloudtelefonzentrale](/microsoftteams/create-a-phone-system-auto-attendant)

   [Beispiel für Kleinunternehmen – Einrichten einer automatischen Telefonzentrale](/microsoftteams/tutorial-org-aa)

   [Erstellen einer Cloudanrufwarteschleife](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[Neu – CsOnlineApplicationInstanceAssociation](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstanceassociation?view=skype-ps)

[Telefonsystem – virtuelle Benutzerlizenz](teams-add-on-licensing/virtual-user.md)
