---
title: Konfigurieren des Cloud Voicemail-Diensts für lokale Benutzer
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
ms.date: 2/11/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Anweisungen zum Implementieren von Cloud-basierter Voicemail für Benutzer, die in Skype for Business Server verwaltet werden.
ms.openlocfilehash: 754d69a9b76497f8776667b6ac97498a151c7e4e
ms.sourcegitcommit: bcac0d94f6eb7132fc17b0ace62e7028f77b0ee6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2020
ms.locfileid: "41230355"
---
# <a name="configure-cloud-voicemail-service-for-on-premises-users"></a>Konfigurieren des Cloud Voicemail-Diensts für lokale Benutzer

## <a name="overview"></a>Übersicht 
In diesem Artikel wird beschrieben, wie Sie den Microsoft Cloud Voicemail-Dienst für Ihre Skype for Business lokalen Benutzern konfigurieren.  

In diesem Artikel wird davon ausgegangen, dass Sie bereits Skype for Business Server in einer unterstützten Topologie bereitgestellt haben und dass Sie die Voraussetzungen für die Einrichtung der Hybrid Konnektivität erfüllt haben.

Weitere Informationen zu den Vorteilen, Planungsüberlegungen und Anforderungen für die Implementierung von Cloud-Voicemail finden Sie unter [Plan Cloud Voicemail Service](plan-cloud-voicemail.md).




Das Konfigurieren der Cloud-Voicemail umfasst die folgenden Aufgaben:

1.  Stellen Sie sicher, dass Sie die Voraussetzungen erfüllt haben, wie unter [Plan Cloud Voicemail Service](plan-cloud-voicemail.md)beschrieben.

2.  Stellen Sie sicher, dass Sie die Hybrid Konnektivität wie unter [Plan Hybrid](plan-hybrid-connectivity.md) Connectivity und [configure Hybrid Connectivity](configure-hybrid-connectivity.md)beschrieben eingerichtet haben. 

3.  [Konfigurieren Sie die Cloud-Voicemail als Hostanbieter auf dem Edgeserver](#configure-cloud-voicemail-as-the-hosting-provider) , wie in diesem Artikel beschrieben.

4.  [Konfigurieren Sie eine Richtlinie für gehostete Voicemail](#configure-a-hosted-voicemail-policy) wie in diesem Artikel beschrieben.

5.  [Weisen Sie eine Richtlinie für gehostete Voicemail](#assign-a-hosted-voicemail-policy) wie in diesem Artikel beschrieben zu.

6.  [Aktivieren Sie einen Benutzer für Cloud-Voicemail](#enable-a-user-for-cloud-voicemail) , wie in diesem Artikel beschrieben.


## <a name="configure-cloud-voicemail-as-the-hosting-provider"></a>Konfigurieren der Cloud-Voicemail als Hostanbieter 

Sie konfigurieren Cloud-Voicemail als Hostanbieter auf einem Front-End-Server mithilfe des New-CsHostingProvider-Cmdlets mit den folgenden Parametern:

- **Identity** gibt einen eindeutigen Bezeichner für den Zeichenfolgenwert für den Hostinganbieter an, den Sie erstellen. beispielsweise Cloud Voicemail. 

- **Enabled** gibt an, ob die Netzwerkverbindung zwischen Ihrer Domäne und dem Hostinganbieter aktiviert ist. Dieser Parameter muss auf true festgelegt werden.

- **EnabledSharedAddressSpace** gibt an, ob der Hostinganbieter in einem Szenario mit freigegebenem SIP-Adressraum verwendet wird. Dieser Parameter muss auf true festgelegt werden.

- **HostsOCSUsers** gibt an, ob der Hostinganbieter zum Hosten von Skype for Business Server Konten verwendet wird. Dieser Parameter muss auf false festgelegt werden.

- **ProxyFQDN** gibt den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für den vom Hostanbieter verwendeten Proxy Server an. Beispiel: Proxyserver.contoso.com. Sie erhalten diese Information von Ihrem Hostinganbieter. Dieser Wert kann nicht geändert werden. Wenn der Hostanbieter seinen Proxy Server ändert, müssen Sie den Eintrag für diesen Anbieter löschen und dann neu erstellen.

- **IsLocal** gibt an, ob der vom Hostinganbieter verwendete Proxy Server in Ihrer Skype for Business Server Topologie enthalten ist. Dieser Parameter muss auf false festgelegt werden.

Beispielsweise konfiguriert das folgende Cmdlet in der Skype for Business Verwaltungsshell die Cloud-Voicemail als Hostanbieter:


```PowerShell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

## <a name="configure-a-hosted-voicemail-policy"></a>Konfigurieren einer Richtlinie für gehostete Voicemail

Um sicherzustellen, dass Voicemail für Ihre Organisation an den Cloud-Voicemaildienst weitergeleitet wird, müssen Sie eine Richtlinie für gehostete Voicemails für Ihre Organisation konfigurieren. In vielen Fällen ist nur eine Richtlinie für gehostete Voicemail erforderlich, und Sie können die globale Richtlinie ändern, um alle Ihre Anforderungen zu erfüllen. Wenn in Ihrer Organisation mehrere Richtlinien für gehostete Voicemails erforderlich sind, können Sie mithilfe des Cmdlets New-cshostedvoicemailpolicy Richtlinien hinzufügen.

Um die globale Richtlinie zu ändern, führen Sie den folgenden Befehl in der Skype for Business Server-Verwaltungsshell aus, nachdem Sie Ihre Organisation und die Mandanten-und Verwaltungskonsole aktualisiert haben:

```PowerShell
Set-CsHostedVoicemailPolicy -Identity Global -Description "Global Cloud Voicemail Policy" -Destination exap.um.outlook.com -Organization YourDefaultDomain.onmicrosoft.com -Tenant “11111111-1111-1111-1111-111111111111”
```

- **Destination** gibt den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des gehosteten Cloud-Voicemail-Diensts an. Dieser Wert sollte auf **exap.um.Outlook.com**festgelegt werden.

- **Organisation** ist die Standarddomäne, die Ihrem Mandanten zugewiesen ist. Sie können diese Informationen abrufen, indem Sie den mandantenadministrator bei Office.com anmelden, auf die Admin Center-App klicken, zu **Setup** auf der linken Seite navigieren und auf **Domänen**klicken. Beispiel: mytenant.onmicrosoft.com.

    Der Name der Organisation ist auch der Standarddomänenname in Office 365.

- **Mandant** wird verwendet, um ihren Mandanten in Office 365 zu identifizieren. Weitere Informationen finden Sie unter [Suchen Ihrer Office 365 Mandanten-ID](https://support.office.com/en-us/article/find-your-office-365-tenant-id-6891b561-a52d-4ade-9f39-b492285e2c9b).

Um sicherzustellen, dass eine Richtlinie für gehostete Voicemail erfolgreich erstellt wurde, führen Sie den folgenden Befehl aus:

```PowerShell
Get-CsHostedVoicemailPolicy
```

## <a name="assign-a-hosted-voicemail-policy"></a>Zuweisen einer Richtlinie für gehostete Voicemail

Standardmäßig wird die globale Richtlinie für gehostete Voicemail allen Benutzern zugewiesen. Wenn Sie eine andere Richtlinie verwenden, müssen Sie vor dem Aktivieren von Benutzern für gehostete Voicemails Benutzern zunächst die gewünschte Richtlinie für gehostete Voicemail erteilen, indem Sie das [Grant-CSHostedVoicemailPolicy-](https://docs.microsoft.com/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) Cmdlet verwenden.

Mit dem folgenden Befehl wird beispielsweise einem Benutzer eine nicht global gehostete Voicemail-Richtlinie zugewiesen:


```PowerShell
Get-CsUser -Identity "User1" | Grant-CsHostedVoicemailPolicy -Identity "Tag:CloudVoiceMailUsers" 
```

## <a name="enable-a-user-for-cloud-voicemail"></a>Aktivieren eines Benutzers für Cloud-Voicemail

Um zu ermöglichen, dass Voicemail-Anrufe eines Benutzers an die Cloud-Voicemail weitergeleitet werden, verwenden Sie das Cmdlet " [CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) " mit dem Parameter "HostedVoiceMail". 

Mit dem folgenden Befehl wird beispielsweise ein Benutzerkonto für die Cloud-Voicemail aktiviert: 

```Set-CsUser -Identity "User1" -HostedVoiceMail $True```

Das Cmdlet überprüft, ob eine Cloud-Voicemail-Richtlinie auf globaler, Standort-oder Benutzerebene für diesen Benutzer gilt. Wenn keine Richtlinie angewendet wird, schlägt das Cmdlet fehl.  

Im nächsten Beispiel wird ein Benutzerkonto für die Cloud-Voicemail deaktiviert:

```Set-CsUser -Identity "User1" -HostedVoiceMail $False```

Das Cmdlet überprüft, ob keine Richtlinie für gehostete Voicemails – auf globaler, Standort-oder Benutzerebene – auf diesen Benutzer angewendet wird. Wenn eine Richtlinie angewendet wird, schlägt das Cmdlet fehl.

> [!NOTE]
>  Benutzer müssen für die Verwendung des Microsoft Cloud Voicemail-Diensts Enterprise-Voice aktiviert sein.
