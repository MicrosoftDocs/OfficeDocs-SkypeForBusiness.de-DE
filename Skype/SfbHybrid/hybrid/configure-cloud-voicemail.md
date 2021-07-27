---
title: Konfigurieren Cloud-Voicemail Diensts für lokale Benutzer
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
ms.date: 2/11/2019
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Anweisungen zum Implementieren von cloudbasierter Voicemail für Benutzer, die auf Skype for Business Server verwaltet werden.
ms.openlocfilehash: 76d65efcc0df59396942c8a38ebc22006427a0f0
ms.sourcegitcommit: 9879bc587382755d9a5cd63a75b0e7dc4e15574c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/21/2021
ms.locfileid: "53510576"
---
# <a name="configure-cloud-voicemail-service-for-on-premises-users"></a>Konfigurieren Cloud-Voicemail Diensts für lokale Benutzer

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


## <a name="overview"></a>Übersicht 
In diesem Artikel wird beschrieben, wie Sie Microsoft Cloud-Voicemail Dienst für Ihre Skype for Business lokalen Benutzer konfigurieren.  

In diesem Artikel wird davon ausgegangen, dass Sie bereits Skype for Business Server in einer unterstützten Topologie bereitgestellt haben und die Voraussetzungen für die Einrichtung der Hybridkonnektivität erfüllt haben.

Weitere Informationen zu den Vorteilen, Planungsüberlegungen und Anforderungen für die Implementierung von Cloud-Voicemail finden Sie unter [Plan Cloud-Voicemail Service.](plan-cloud-voicemail.md)




Das Konfigurieren Cloud-Voicemail umfasst die folgenden Aufgaben:

1.  Stellen Sie sicher, dass die Voraussetzungen erfüllt sind, wie unter [Plan Cloud-Voicemail Service](plan-cloud-voicemail.md)beschrieben.

2.  Stellen Sie sicher, dass Sie die Hybridkonnektivität wie unter Planen der [Hybridkonnektivität](plan-hybrid-connectivity.md) und [Konfigurieren der Hybridkonnektivität](configure-hybrid-connectivity.md)beschrieben eingerichtet haben. 

3.  [Konfigurieren Sie Cloud-Voicemail als Hostinganbieter auf dem Front-End-Server,](#configure-cloud-voicemail-as-the-hosting-provider) wie in diesem Artikel beschrieben.

4.  [Konfigurieren Sie eine gehostete Voicemailrichtlinie,](#configure-a-hosted-voicemail-policy) wie in diesem Artikel beschrieben.

5.  [Weisen Sie eine gehostete Voicemailrichtlinie](#assign-a-hosted-voicemail-policy) zu, wie in diesem Artikel beschrieben.

6.  [Aktivieren Sie einen Benutzer für Cloud-Voicemail,](#enable-a-user-for-cloud-voicemail) wie in diesem Artikel beschrieben.


## <a name="configure-cloud-voicemail-as-the-hosting-provider"></a>Konfigurieren Cloud-Voicemail als Hostinganbieter 

Sie konfigurieren Cloud-Voicemail als Hostinganbieter auf einem Front-End-Server mithilfe des Cmdlets New-CsHostingProvider mit den folgenden Parametern:

- **Die Identität** gibt einen eindeutigen Zeichenfolgenwertbezeichner für den Hostinganbieter an, den Sie erstellen. Beispielsweise Cloud-Voicemail. 

- **Enabled** gibt an, ob die Netzwerkverbindung zwischen Ihrer Domäne und dem Hostinganbieter aktiviert ist. Dieser Parameter muss auf "True" festgelegt sein.

- **EnabledSharedAddressSpace** gibt an, ob der Hostinganbieter in einem Szenario mit freigegebenem SIP-Adressraum verwendet wird. Dieser Parameter muss auf "True" festgelegt sein.

- **HostsOCSUsers** gibt an, ob der Hostinganbieter zum Hosten Skype for Business Server Konten verwendet wird. Dieser Parameter muss auf "False" festgelegt sein.

- **ProxyFQDN** gibt den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für den vom Hostinganbieter verwendeten Proxyserver an. Beispielsweise proxyserver.contoso.com. Sie erhalten diese Information von Ihrem Hostinganbieter. Dieser Wert kann nicht geändert werden. Wenn der Hostinganbieter seinen Proxyserver ändert, müssen Sie den Eintrag für diesen Anbieter löschen und dann erneut erstellen.

- **IsLocal** gibt an, ob der vom Hostinganbieter verwendete Proxyserver in Ihrer Skype for Business Server Topologie enthalten ist. Dieser Parameter muss auf "False" festgelegt sein.

Beispielsweise konfiguriert das folgende Cmdlet in der Skype for Business-Verwaltungsshell Cloud-Voicemail als Hostinganbieter:


```PowerShell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

## <a name="configure-a-hosted-voicemail-policy"></a>Konfigurieren einer gehosteten Voicemailrichtlinie

Um sicherzustellen, dass Voicemail für Ihre Organisation an den Cloud-Voicemail Dienst weitergeleitet wird, müssen Sie eine gehostete Voicemailrichtlinie für Ihre Organisation konfigurieren. In vielen Fällen ist nur eine gehostete Voicemailrichtlinie erforderlich, und Sie können die globale Richtlinie an alle Ihre Anforderungen anpassen. Wenn Ihre Organisation mehrere gehostete Voicemailrichtlinien erfordert, können Sie Richtlinien mithilfe des Cmdlets "new-cshostedvoicemailpolicy" hinzufügen.

Um die globale Richtlinie zu ändern, führen Sie den folgenden Befehl in der Skype for Business Server Verwaltungsshell aus, nachdem Sie Ihre Organisation und Mandanten-ID aktualisiert haben:

```PowerShell
Set-CsHostedVoicemailPolicy -Identity Global -Description "Global Cloud Voicemail Policy" -Destination exap.um.outlook.com -Organization YourDefaultDomain.onmicrosoft.com
```

- **Destination** specifies the fully qualified domain name (FQDN) of the hosted Cloud-Voicemail service. Dieser Wert sollte auf **exap.um.outlook.com** festgelegt werden.

- **Die Organisation** ist die Standarddomäne, die Ihrem Mandanten zugewiesen ist. Sie können diese Informationen abrufen, indem Sie sich vom Mandantenadministrator bei office.com anmelden, auf die Admin Center-App klicken, links zu **Setup** navigieren und auf **Domänen** klicken. Beispiel: mytenant.onmicrosoft.com.

    Der Organisationsname ist auch der Standarddomänenname in Microsoft 365 oder Office 365.

Führen Sie den folgenden Befehl aus, um sicherzustellen, dass eine gehostete Voicemailrichtlinie erfolgreich erstellt wurde:

```PowerShell
Get-CsHostedVoicemailPolicy
```

## <a name="assign-a-hosted-voicemail-policy"></a>Zuweisen einer gehosteten Voicemailrichtlinie

Standardmäßig wird die global gehostete Voicemailrichtlinie allen Benutzern zugewiesen. Wenn Sie eine andere Richtlinie verwenden, müssen Sie Benutzern vor dem Aktivieren von Benutzern für gehostete Voicemail zuerst die gewünschte gehostete Voicemailrichtlinie mithilfe des [Cmdlets Grant-CSHostedVoicemailPolicy](/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) erteilen.

Beispielsweise weist der folgende Befehl einem Benutzer eine nicht-globale gehostete Voicemailrichtlinie zu:


```PowerShell
Get-CsUser -Identity "User1" | Grant-CsHostedVoicemailPolicy -PolicyName "Tag:CloudVoiceMailUsers" 
```

## <a name="enable-a-user-for-cloud-voicemail"></a>Aktivieren eines Benutzers für Cloud-Voicemail

Damit die Voicemailanrufe eines Benutzers an Cloud-Voicemail weitergeleitet werden können, verwenden Sie das Cmdlet ["Set-CsUser"](/powershell/module/skype/set-csuser?view=skype-ps) mit dem Parameter "HostedVoiceMail". 

Mit dem folgenden Befehl wird beispielsweise ein Benutzerkonto für Cloud-Voicemail aktiviert: 

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $True
```

Das Cmdlet überprüft, ob eine Cloud-Voicemail-Richtlinie – auf globaler, Standort- oder Benutzerebene – für diesen Benutzer gilt. Wenn keine Richtlinie gilt, schlägt das Cmdlet fehl.  

Im nächsten Beispiel wird ein Benutzerkonto für Cloud-Voicemail deaktiviert:

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $False
```

Das Cmdlet überprüft, ob keine gehostete Voicemailrichtlinie – auf globaler, Standort- oder Benutzerebene – für diesen Benutzer gilt. Wenn eine Richtlinie gilt, schlägt das Cmdlet fehl.

> [!NOTE]
>  Benutzer müssen enterprise-voIP aktiviert sein, um den Microsoft Cloud-Voicemail Dienst verwenden zu können.