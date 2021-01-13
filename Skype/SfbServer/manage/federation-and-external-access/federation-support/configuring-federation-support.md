---
title: Konfigurieren der Unterstützung für Partnerverbund bei einem Skype for Business Online-Kunden
ms.reviewer: ''
ms:assetid: e5f7f38d-ede5-4af3-88c2-026e8a78df12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202193(v=OCS.15)
ms:contentKeyID: 48185669
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Wenn Sie Skype for Business in Ihrer Organisation bereitstellen, können Sie einen Verbund mit den Domänen eines oder mehreren Skype for Business Online-Kunden einrichten. '
ms.openlocfilehash: f09e717af9e5209a0bb4bfdeb0ea50abbdaf7f86
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817235"
---
# <a name="configuring-federation-support-for-a-skype-for-business-online-customer-in-skype-for-business-server"></a>Konfigurieren der Verbundunterstützung für einen Skype for Business Online-Kunden in Skype for Business Server 

Sie können Benutzern in Ihrer Organisation auf die folgende Art Kommunikationsdienste bieten:

  - Bereitstellen von Skype for Business Server in Ihrer Organisation (auch als lokale Dienste bezeichnet) und Einrichten von Skype for *Business-Benutzerkonten* in Ihrer Organisation.
  - Einrichten eines Microsoft Skype for Business Online-Kundenkontos bei einem Hostinganbieter und Einrichten von Benutzerkonten beim Hostinganbieter (auch als *Onlinedienste bekannt).*

Wenn Sie Skype for Business in Ihrer Organisation bereitstellen, können Sie einen Verbund mit den Domänen eines oder mehreren Skype for Business Online-Kunden einrichten. Zum Aktivieren des Verbunds zwischen Benutzern Ihrer lokalen Skype for Business-Bereitstellung und Benutzern eines Skype for Business Online-Kunden müssen Sie den Support für die Domäne und die Benutzer des Skype for Business Online-Kunden konfigurieren.

> [!NOTE]  
> In dieser Dokumentation werden nur die Verfahren zum Konfigurieren Ihrer Organisation zur Unterstützung des Verbunds mit einem Skype for Business Online-Kunden beschrieben. In dieser Dokumentation werden die Verfahren zum Konfigurieren des Skype for Business Online-Kunden zur Unterstützung des Verbunds nicht beschrieben. 

## <a name="prerequisites-for-federating-with-a-skype-for-business-online-customer"></a>Voraussetzungen für den Verbund mit einem Skype for Business Online-Kunden

Um mit einem Skype for Business Online-Kunden im Verbund zu arbeiten, sollten Sie die Erstbereitstellung und Konfiguration von Skype for Business Server in Ihrer Organisation bereits abgeschlossen haben. Dazu gehört Folgendes:

  - Bereitstellen von mindestens einem Standard Edition-Server oder einem Enterprise Edition-Front-End-Pool in Ihrer Organisation. 
  - Aktivieren interner Benutzerkonten für Skype for Business Server. 
  - Bereitstellen von mindestens einem Edgeserver und den anderen Komponenten, die zur Unterstützung des Zugriffs durch externe Benutzer erforderlich sind. Weitere Informationen finden Sie [unter Verwalten des Verbunds und des externen Zugriffs auf Skype for Business Server.](../managing-federation-and-external-access.md)
  - Aktivieren der Partnerverbundunterstützung innerhalb Ihrer Organisation und Konfigurieren der geeigneten Methode zum Steuern des Zugriffs durch Verbunddomänen. Weitere Informationen finden Sie unter "Aktivieren oder [Deaktivieren des Remotebenutzerzugriffs"](../access-edge/enable-or-disable-remote-user-access.md) und ["Verwalten von SIP-Verbundanbietern für Ihre Organisation".](../sip-providers/manage-sip-federated-providers-for-your-organization.md)
  - Aktivieren des Externen Benutzerzugriffs für Benutzer in Ihrer Organisation. Weitere Informationen finden Sie unter [Assign an external user access policy to a Skype for Business enabled user](../external-access-policies/assign-an-external-user-access-policy.md).



## <a name="configure-federation-support-for-a-skype-for-business-online-domain"></a>Konfigurieren der Verbundunterstützung für eine Skype for Business Online-Domäne

Für den Partnerbetrieb mit einem Skype for Business Online-Kunden müssen Sie die folgenden Schritte ausführen:

  - Konfigurieren Sie die Unterstützung für die Domäne des Skype for Business Online 2010-Kunden (z. B. contoso.onmicrosoft.com). Wie unter ["Voraussetzungen für den Partnerverbund](#prerequisites-for-federating-with-a-skype-for-business-online-customer)mit einem Skype for Business Online-Kunden" angegeben, sollten Sie den Partnerverbund für Ihre Organisation bereits aktiviert haben. Zum Aktivieren des Partnerverbunds muss die Methode zur Steuerung des Zugriffs durch Partnerdomänen angegeben werden. Wenn in Ihrer Organisation die Ermittlung verwendet wird, kann die Domäne optional der Liste der zugelassenen Domänen Ihrer Organisation hinzugefügt werden. Wenn Sie die Domänenermittlung nicht aktiviert haben, müssen Sie den Domänennamen des Skype for Business Online-Kunden zur Liste der zulässigen Domänen hinzufügen. Sie können einen Domänennamen entweder mithilfe der Skype for Business Server-Systemsteuerung oder durch Ausführen des **Cmdlets "New-CSAllowedDomain"** hinzufügen. Details zur Verwendung der Skype for Business Server-Systemsteuerung, einschließlich der Aktivierung der Suche nach Domänen, finden Sie unter Verwalten von SIP-Verbundanbietern für Ihre Organisation [in Skype for Business Server.](../sip-providers/manage-sip-federated-providers-for-your-organization.md) Weitere Informationen zur Verwendung des **Cmdlets "New-CSAllowedDomain"** zum Hinzufügen einer Domäne finden Sie unter ["New-CsAllowedDomain".](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain)

    > [!NOTE]  
    > Ein Skype for Business Online-Kunde kann mehrere Domänen haben. Wenn Sie einen Partnerverbund mit mehr als einer der Domänen einrichten möchten, müssen Sie die Unterstützung für jede einzelne Domäne konfigurieren, mit der Sie den Partnerverbund unterstützen möchten, und der Administrator des Skype for Business Online-Kunden muss den Partnerverbund für jede der Domänen aktivieren.

  - Konfigurieren Sie die Unterstützung für den Hostinganbieter der Skype for Business Online-Kundendomäne, mit der Sie einen Verbund erstellen möchten. Verwenden Sie das Verfahren in diesem Abschnitt, um die Unterstützung für Hostinganbieter zu konfigurieren.

    > [!NOTE]  
    > Dieser Schritt ist nur für den Partnerverbund mit einer Domäne eines Skype for Business Online-Kunden erforderlich, nicht für den Partnerverbund mit einer Domäne, die lokal am Standort eines Verbundpartners bereitgestellt wird.


### <a name="to-configure-support-for-a-hosting-provider"></a>So konfigurieren Sie die Unterstützung für einen Hostinganbieter

1.  Starten Sie auf einem Front-End-Server die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **"Start",**"Alle Programme", **"Skype for Business Server"** und dann auf **"Skype for Business Server-Verwaltungsshell".**

2.  Führen Sie das Cmdlet **New-CsHostingProvider** aus, um den Hostinganbieter zu erstellen und zu konfigurieren. Führen Sie beispielsweise den folgenden Befehl aus:
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    Im oben stehenden Beispiel werden folgende Parameter festgelegt:
    
      - **Identity** gibt einen eindeutigen Zeichenfolgenwert für den Hostinganbieter an, den Sie erstellen. Beachten Sie, dass der Befehl nicht erfolgreich ist, wenn bereits ein Anbieter mit dieser Identität konfiguriert wurde.
    
      - **ProxyFQDN** gibt den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des vom Hostinganbieter verwendeten Proxyservers an. Dieser Wert kann nicht geändert werden. Wenn der Hostinganbieter seinen Proxyserver ändert, muss der Eintrag für diesen Anbieter gelöscht und neu erstellt werden.
    
      - **VerificationLevel** gibt an, wie (oder ob) von einem Hostinganbieter gesendete Nachrichten überprüft werden, um sicherzustellen, dass sie tatsächlich von diesem Anbieter stammen.
    
      - **Enabled** gibt an, ob die Netzwerkverbindung zwischen Ihrer Domäne und dem Hostinganbieter aktiviert ist. Der Nachrichtenaustausch zwischen zwei Organisationen ist erst möglich, wenn dieser Wert auf **True** festgelegt ist.
    
      - **EnabledSharedAddressSpace** gibt an, ob der Hostinganbieter in einem Szenario mit freigegebenem SIP-Adressraum (getrennte Domäne) verwendet wird.
    
      - **HostsOCSUsers** gibt an, ob der Hostinganbieter zum Hosten von Skype for Business Server-Konten verwendet wird. Der Wert **False** gibt an, dass der Anbieter andere Kontotypen (z. B. Microsoft Exchange-Konten) hostet.
    
      - **IsLocal** gibt an, ob der vom Hostinganbieter verwendete Proxyserver in Ihrer Skype for Business Server-Topologie enthalten ist.
    
    Weitere Informationen zur Verwendung dieses Cmdlets finden Sie unter [New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider).

## <a name="configure-user-access-for-federation-with-a-skype-for-business-online-customer"></a>Konfigurieren des Benutzerzugriffs für den Verbund mit einem Skype for Business Online-Kunden 

Sie müssen die Benutzerkonten aller Benutzer in der Organisation so konfigurieren, dass die Kommunikation mit Verbundpartnern zulässig ist. Diese Konfiguration wird für alle Verbundpartner angewendet, einschließlich aller Microsoft Skype for Business Online-Kundendomänen, mit denen Sie den Partnerverbund unterstützen. Weitere Informationen zum Konfigurieren der Verbundunterstützung [](../external-access-policies/configure-policies-to-control-federated-user-access.md) für Benutzerkonten finden Sie unter "Konfigurieren von Richtlinien zum Steuern des Zugriffs durch Partnerbenutzer" und zuweisen einer Richtlinie für den externen Benutzerzugriff zu einem [skype for Business-aktivierten Benutzer.](../external-access-policies/assign-an-external-user-access-policy.md)

## <a name="verify-communications-with-a-skype-for-business-online-customer-in-skype-for-business-server"></a>Überprüfen der Kommunikation mit einem Skype for Business Online-Kunden in Skype for Business Server

Damit Skype for Business-Benutzer in Ihrer Organisation mit Benutzern eines Skype for Business Online-Kunden kommunizieren können, müssen Sie die folgenden Schritte durchgeführt haben:

  - Erfüllt alle Voraussetzungen. Dies umfasst die Bereitstellung ihrer internen Server und Edgeserver, das Aktivieren der Verbundunterstützung für Ihre Organisation und das Einrichten von Benutzerkonten. Weitere Informationen finden Sie unter Voraussetzungen für den Verbund mit einem [Skype for Business Online-Kunden.](#prerequisites-for-federating-with-a-skype-for-business-online-customer)
  - Konfigurierte Domänenzugriffsunterstützung in Ihrer internen Bereitstellung. Dies umfasst das Erstellen eines Hostanbietereintrags und das Konfigurieren Ihrer Bereitstellung, um den Zugriff über die Domäne des Skype for Business Online-Kunden zu ermöglichen. Weitere Informationen finden Sie unter ["Konfigurieren der Verbundunterstützung für eine Skype for Business Online-Domäne".](#configure-federation-support-for-a-skype-for-business-online-domain)
  - Die Benutzerkonten wurden für die Unterstützung des Verbunds konfiguriert. Weitere Informationen finden Sie unter ["Konfigurieren des Benutzerzugriffs für den Verbund mit einem Skype for Business Online-Kunden".](#configure-user-access-for-federation-with-a-skype-for-business-online-customer)

Nachdem Sie alle diese Schritte abgeschlossen haben und der Administrator des Skype for Business Online-Kunden alle Konfigurationen seiner Onlinedienste abgeschlossen hat, um den Verbund mit Ihrer Organisation zu unterstützen, überprüfen Sie die Kommunikation, indem Sie die Kommunikation zwischen einem internen Benutzer in Ihrer Organisation und einem Benutzer des Skype for Business Online-Kunden testen. Wenn die Kommunikation nicht erfolgreich ist, verwenden Sie das Protokollierungstool von Ihrem Edgeserver, um Protokoll- und Ablaufverfolgungsdateien zu erfassen, um das Problem zu beheben. 
