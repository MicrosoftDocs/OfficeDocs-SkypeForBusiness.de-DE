---
title: Konfigurieren von Voicemail von Cloud-Dienst
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 5/9/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Anweisungen zum Implementieren der Cloud-basierten Voicemail für Benutzer, der in Skype für Business Server verwaltet.
ms.openlocfilehash: 9cc990cbaecfea74b269809d9e31588d61eee93c
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027816"
---
# <a name="configure-cloud-voicemail-service"></a>Konfigurieren von Voicemail von Cloud-Dienst


[!INCLUDE [disclaimer](../disclaimer.md)]

## <a name="overview"></a>Übersicht 
In diesem Artikel wird beschrieben, wie Microsoft Cloud Voicemail-Dienst für Ihre Skype für lokale Geschäftsbenutzer konfigurieren.  

In diesem Artikel wird davon ausgegangen, dass Sie bereits Skype für Business Server in einer unterstützten Topologie bereitgestellt haben und dass Sie die erforderlichen Komponenten für das Einrichten von hybridkonnektivität erfüllt sind.

Weitere Informationen zu den Vorteilen Planungsaspekte, und Anforderungen für die Implementierung von Cloud-Voicemail finden Sie unter [Planen der Cloud Voicemail Service](plan-cloud-voicemail.md).




Konfigurieren von Cloud-Voicemail umfasst die folgenden Aufgaben:

1.  Stellen Sie sicher, dass Sie die erforderlichen Komponenten erfüllt sind, wie in der [Cloud Voicemail planen Service](plan-cloud-voicemail.md)beschrieben.

2.  Stellen Sie sicher, dass Sie hybridkonnektivität wie beschrieben unter [hybridkonnektivität Plan](plan-hybrid-connectivity.md) and [Configure hybridkonnektivität](configure-hybrid-connectivity.md)eingerichtet haben. 

3.  [Konfigurieren von Cloud Voicemail als Hostinganbieter auf dem Edge-Server](#configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server) wie in diesem Artikel beschrieben.

4.  [Konfigurieren einer voicemailrichtlinie für gehostete](#configure-a-hosted-voicemail-policy) wie in diesem Artikel beschrieben.

5.  [Zuweisen einer voicemailrichtlinie für gehostete](#assign-a-hosted-voicemail-policy) , wie in diesem Artikel beschrieben.

6.  [Aktivieren eines Benutzers für Cloud Voicemail](#enable-a-user-for-cloud-voicemail) , wie in diesem Artikel beschrieben.


## <a name="configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server"></a>Konfigurieren von Cloud-Voicemail als Hostinganbieter auf dem Edge-Server 

Sie können Cloud Voicemail als Hostinganbieter auf dem Edge-Server konfigurieren, mit dem New-CsHostingProvider-Cmdlet mit den folgenden Parametern:

- **Identität** gibt einen eindeutigen Zeichenfolgenwert für den Hostinganbieter, den Sie erstellen. beispielsweise Cloud Voicemail. 

- **Enabled** gibt an, ob die Netzwerkverbindung zwischen Ihrer Domäne und dem Hostinganbieter aktiviert ist. Dieser Parameter muss auf True festgelegt werden.

- **EnabledSharedAddressSpace** gibt an, ob der Hostinganbieter in einem freigegebenen SIP-Adresse Speicherplatz Szenario verwendet wird. Dieser Parameter muss auf True festgelegt werden.

- **HostsOCSUsers** gibt an, ob der Hostinganbieter zum Hosten von Skype für Business Server-Konten verwendet wird. Dieser Parameter muss auf False festgelegt.

- **ProxyFQDN** gibt den vollqualifizierten Domänennamen (FQDN) für die vom Hostinganbieter verwendete Proxyserver an. beispielsweise proxyserver.contoso.com. Diese Informationen erhalten Sie bei Ihrem Hostinganbieter. Dieser Wert kann nicht geändert werden. Wenn der Hostinganbieter seine Proxyserver ändert, müssen Sie löschen und Neuerstellen klicken Sie dann den Eintrag für den Anbieter.

- **IsLocal** gibt an, ob der vom Hostinganbieter verwendete Proxyserver in Ihrer Skype für Business Server-Topologie enthalten ist. Dieser Parameter muss auf False festgelegt.

Beispielsweise konfiguriert das folgende Cmdlet in der Skype für Business-Verwaltungsshell, Cloud Voicemail als Hostinganbieter:


```
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

## <a name="configure-a-hosted-voicemail-policy"></a>Konfigurieren einer voicemailrichtlinie für gehostete

Um sicherzustellen, dass Voicemail für Ihre Organisation an die Voicemail Cloud-Dienst weitergeleitet werden, müssen Sie eine gehostete voicemailrichtlinie für Ihre Organisation konfigurieren. In vielen Fällen nur eine gehostete voicemailrichtlinie ist erforderlich, und Sie können die globale Richtlinie alle Ihre Bedürfnisse ändern. Wenn Ihre Organisation mehrere Richtlinien für gehostete Voicemail erfordert, können Sie Richtlinien hinzufügen, mit dem Cmdlet new-Cshostedvoicemailpolicy.

Um die globale Richtlinie zu ändern, führen Sie den folgenden Befehl in der Skype für Business Server-Verwaltungsshell nach dem Aktualisieren Ihrer Organisation und die TenantID:

```
Set-CsHostedVoicemailPolicy -Identity Global -Description "Global Cloud Voicemail Policy" -Destination exap.um.outlook.com -Organization YourDefaultDomain.onmicrosoft.com -TenantID “11111111-1111-1111-1111-111111111111”
```

- **Ziel** gibt den vollqualifizierten Domänennamen (FQDN) des gehosteten Cloud Voicemail-Diensts an. Dieser Wert sollte auf **exap.um.outlook.com**festgelegt werden.

- **Organisation** ist die Standarddomäne, die Ihre Mandanten zugewiesen. Sie können diese Informationen abrufen, indem Sie den Administrator des Mandanten melden Sie sich bei office.com, klicken Sie auf der app-Verwaltungskonsole, navigieren Sie auf der linken Seite **des Setups** und klicken Sie auf **Domänen**. Beispiel: mytenant.onmicrosoft.com.

    Der Name der Organisation ist auch den Standard-Domänennamen in Office 365.

- **TenantID** wird verwendet, um Ihren Office 365-Mandanten zu identifizieren. Weitere Informationen finden Sie unter [Suchen Sie nach Ihrer Office 365-Mandanten-ID](https://support.office.com/en-us/article/find-your-office-365-tenant-id-6891b561-a52d-4ade-9f39-b492285e2c9b).

Um sicherzustellen, dass eine voicemailrichtlinie für gehostete erfolgreich erstellt wurde, führen Sie den folgenden Befehl aus:

```
Get-CsHostedVoicemailPolicy
```

## <a name="assign-a-hosted-voicemail-policy"></a>Zuweisen einer voicemailrichtlinie für gehostete

Standardmäßig Global gehostete voicemailrichtlinie für alle Benutzer zugewiesen ist. Wenn Sie eine andere Richtlinie, bevor Sie Benutzer für gehostete Voicemail aktivieren verwenden, müssen Sie zunächst Benutzer der gewünschten gehostete voicemailrichtlinie erteilen mithilfe des Cmdlets [Grant-CSHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) .

Beispielsweise weist der folgende Befehl ein nicht-globalen gehosteten voicemailrichtlinie, die einem Benutzer:


```
Get-CsUser -Identity "User1" | Grant-CsHostedVoicemailPolicy -Identity "Tag:CloudVoiceMailUsers" 
```

## <a name="enable-a-user-for-cloud-voicemail"></a>Aktivieren eines Benutzers für die Cloud-Voicemail

Zum Aktivieren eines Benutzers Voicemail Anrufen an die Cloud Voicemail weitergeleitet werden sollen, verwenden Sie das [Set-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/set-csuser?view=skype-ps) -Cmdlet mit dem Parameter HostedVoiceMail. 

Beispielsweise kann der folgende Befehl ein Benutzerkonto für Cloud Voicemail: 

```Set-CsUser -Identity "User1" -HostedVoiceMail $True```

Das Cmdlet prüft, ob eine Cloud Voicemail-Richtlinie – auf global, Standort oder auf Benutzerebene – gilt für diesen Benutzer. Wenn keine Richtlinie angewendet wird, schlägt das Cmdlet fehl.  

Im nächste Beispiel wird ein Benutzerkonto für Cloud Voicemail deaktiviert:

```Set-CsUser -Identity "User1" -HostedVoiceMail $False```

Das Cmdlet prüft, ob keine gehosteten voicemailrichtlinie--auf globaler, Website oder auf Benutzerebene – gilt für diesen Benutzer. Wenn eine Richtlinie gilt, schlägt das Cmdlet fehl.

> [!NOTE]
>  Benutzer müssen Enterprise-VoIP aktiviert sind, um Voicemail Microsoft Cloud-Dienst verwenden können.