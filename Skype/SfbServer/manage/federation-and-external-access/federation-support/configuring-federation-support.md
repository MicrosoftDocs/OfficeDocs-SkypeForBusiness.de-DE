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
description: 'Wenn Sie Skype for Business in Ihrer Organisation bereitstellen, können Sie einen Verbund mit den Domänen eines oder mehreren Skype for Business Online-Kunden erstellen. '
ms.openlocfilehash: c241af4700662c11366a71a55afad28ed3f8b7db
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098951"
---
# <a name="configuring-federation-support-for-a-skype-for-business-online-customer-in-skype-for-business-server"></a>Konfigurieren der Verbundunterstützung für einen Skype for Business Online-Kunden in Skype for Business Server 

Sie können Benutzern in Ihrer Organisation auf die folgende Art Kommunikationsdienste bieten:

  - Bereitstellen von Skype for Business Server in Ihrer Organisation (auch als lokale Dienste bezeichnet) und Einrichten von Skype for *Business-Benutzerkonten* in Ihrer Organisation.
  - Einrichten eines Microsoft Skype for Business Online-Kundenkontos bei einem Hostinganbieter und Einrichten von Benutzerkonten beim Hostinganbieter (als *Onlinedienste bekannt).*

Wenn Sie Skype for Business in Ihrer Organisation bereitstellen, können Sie einen Verbund mit den Domänen eines oder mehreren Skype for Business Online-Kunden erstellen. Zum Aktivieren des Verbunds zwischen Benutzern Ihrer lokalen Skype for Business-Bereitstellung und Benutzern eines Skype for Business Online-Kunden müssen Sie den Support für die Domäne und die Benutzer des Skype for Business Online-Kunden konfigurieren.

> [!NOTE]  
> In dieser Dokumentation werden nur die Verfahren zum Konfigurieren Ihrer Organisation zur Unterstützung des Verbunds mit einem Skype for Business Online-Kunden beschrieben. In dieser Dokumentation werden die Verfahren zum Konfigurieren des Skype for Business Online-Kunden für den Supportverbund nicht beschrieben. 

## <a name="prerequisites-for-federating-with-a-skype-for-business-online-customer"></a>Voraussetzungen für die Zusammenarbeit mit einem Skype for Business Online-Kunden

Zum Verbinden mit einem Skype for Business Online-Kunden sollten Sie bereits die erste Bereitstellung und Konfiguration von Skype for Business Server in Ihrer Organisation abgeschlossen haben. Dazu gehört Folgendes:

  - Bereitstellen von mindestens einem Standard Edition-Server oder einem Enterprise Edition-Front-End-Pool in Ihrer Organisation. 
  - Aktivieren interner Benutzerkonten für Skype for Business Server. 
  - Bereitstellen von mindestens einem Edgeserver und den anderen Komponenten, die für die Unterstützung des externen Benutzerzugriffs erforderlich sind. Weitere Informationen finden Sie [unter Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).
  - Aktivieren der Verbundunterstützung innerhalb Ihrer Organisation und Konfigurieren der entsprechenden Methode zum Steuern des Zugriffs durch Verbunddomänen. Weitere Informationen finden Sie unter [Aktivieren oder Deaktivieren des Remotebenutzerzugriffs](../access-edge/enable-or-disable-remote-user-access.md) und Verwalten von [SIP-Verbundanbietern für Ihre Organisation.](../sip-providers/manage-sip-federated-providers-for-your-organization.md)
  - Aktivieren des externen Benutzerzugriffs für Benutzer in Ihrer Organisation. Weitere Informationen finden Sie unter [Assign an external user access policy to a Skype for Business enabled user](../external-access-policies/assign-an-external-user-access-policy.md).



## <a name="configure-federation-support-for-a-skype-for-business-online-domain"></a>Konfigurieren der Verbundunterstützung für eine Skype for Business Online-Domäne

Für die Zusammenarbeit mit einem Skype for Business Online-Kunden müssen Sie die folgenden Schritte ausführen:

  - Konfigurieren sie den Support für die Domäne des Skype for Business Online 2010-Kunden (z. B. contoso.onmicrosoft.com). Wie unter [Voraussetzungen für das Partnerverbund](#prerequisites-for-federating-with-a-skype-for-business-online-customer)mit einem Skype for Business Online-Kunden angegeben, sollten Sie den Partnerverbund für Ihre Organisation bereits aktiviert haben. Zum Aktivieren des Partnerverbunds muss die Methode zur Steuerung des Zugriffs durch Partnerdomänen angegeben werden. Wenn in Ihrer Organisation die Ermittlung verwendet wird, kann die Domäne optional der Liste der zugelassenen Domänen Ihrer Organisation hinzugefügt werden. Wenn Sie die Domänenermittlung nicht aktiviert haben, müssen Sie den Domänennamen des Skype for Business Online-Kunden zur Liste der zulässigen Domänen hinzufügen. Sie können einen Domänennamen entweder mithilfe der Skype for Business Server-Systemsteuerung oder durch Ausführen des **Cmdlets New-CSAllowedDomain** hinzufügen. Weitere Informationen zur Verwendung der Skype for Business Server-Systemsteuerung, einschließlich der Aktivierung der Domänensuche, finden Sie unter Verwalten von SIP-Verbundanbietern für Ihre Organisation [in Skype for Business Server](../sip-providers/manage-sip-federated-providers-for-your-organization.md). Weitere Informationen zur Verwendung des **Cmdlets New-CSAllowedDomain** zum Hinzufügen einer Domäne finden Sie unter [New-CsAllowedDomain](/powershell/module/skype/New-CsAllowedDomain).

    > [!NOTE]  
    > Ein Skype for Business Online-Kunde kann mehrere Domänen haben. Wenn Sie einen Verbund mit mehr als einer der Domänen erstellen möchten, müssen Sie die Unterstützung für jede einzelne Domäne konfigurieren, mit der Sie den Partnerverbund unterstützen möchten, und der Administrator des Skype for Business Online-Kunden muss den Partnerverbund für jede der Domänen aktivieren.

  - Konfigurieren Sie den Support für den Hostinganbieter der Skype for Business Online-Kundendomäne, mit der Sie einen Verbund erstellen möchten. Verwenden Sie das Verfahren in diesem Abschnitt, um die Unterstützung für Hostinganbieter zu konfigurieren.

    > [!NOTE]  
    > Dieser Schritt ist nur für den Partnerverbund mit einer Domäne eines Skype for Business Online-Kunden erforderlich, nicht für den Partnerverbund mit einer Domäne, die lokal am Standort eines Partnerverbundpartners bereitgestellt wird.


### <a name="to-configure-support-for-a-hosting-provider"></a>So konfigurieren Sie die Unterstützung für einen Hostinganbieter

1.  Starten Sie auf einem Front-End-Server die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start,** klicken Sie auf **Alle** Programme, **klicken Sie auf Skype for Business Server,** und klicken Sie dann auf **Skype for Business Server Management Shell**.

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
    
    Weitere Informationen zur Verwendung dieses Cmdlets finden Sie unter [New-CsHostingProvider](/powershell/module/skype/New-CsHostingProvider).

## <a name="configure-user-access-for-federation-with-a-skype-for-business-online-customer"></a>Konfigurieren des Benutzerzugriffs für den Verbund mit einem Skype for Business Online-Kunden 

Sie müssen die Benutzerkonten aller Benutzer in der Organisation so konfigurieren, dass die Kommunikation mit Verbundpartnern zulässig ist. Diese Konfiguration wird für alle Partnerverbundpartner angewendet, einschließlich aller Microsoft Skype for Business Online-Kundendomänen, mit denen Sie den Partnerverbund unterstützen. Weitere Informationen zum Konfigurieren der Verbundunterstützung für Benutzerkonten finden Sie unter [Configure policies to control federated user access](../external-access-policies/configure-policies-to-control-federated-user-access.md) und Assign an external user access policy to a Skype for Business enabled [user](../external-access-policies/assign-an-external-user-access-policy.md).

## <a name="verify-communications-with-a-skype-for-business-online-customer-in-skype-for-business-server"></a>Überprüfen der Kommunikation mit einem Skype for Business Online-Kunden in Skype for Business Server

Damit Skype for Business-Benutzer in Ihrer Organisation mit Benutzern eines Skype for Business Online-Kunden kommunizieren können, müssen Sie die folgenden Schritte durchgeführt haben:

  - Alle Voraussetzungen erfüllt. Dazu gehören die Bereitstellung ihrer internen Server und Edgeserver, die Aktivierung der Verbundunterstützung für Ihre Organisation und das Einrichten von Benutzerkonten. Weitere Informationen finden Sie unter Voraussetzungen für die Zusammenarbeit mit einem [Skype for Business Online-Kunden.](#prerequisites-for-federating-with-a-skype-for-business-online-customer)
  - Konfigurierte Domänenzugriffsunterstützung in Ihrer internen Bereitstellung. Dies umfasst das Erstellen eines Hostanbietereintrags und die Konfiguration Ihrer Bereitstellung, um den Zugriff über die Domäne des Skype for Business Online-Kunden zu ermöglichen. Weitere Informationen finden Sie unter [Configure federation support for a Skype for Business Online domain](#configure-federation-support-for-a-skype-for-business-online-domain).
  - Konfigurierte Benutzerkonten zur Unterstützung des Verbunds. Weitere Informationen finden Sie [unter Configure user access for federation with a Skype for Business Online customer](#configure-user-access-for-federation-with-a-skype-for-business-online-customer).

Nachdem Sie alle diese Schritte abgeschlossen haben und der Administrator des Skype for Business Online-Kunden alle Konfigurationen seiner Onlinedienste abgeschlossen hat, um den Verbund mit Ihrer Organisation zu unterstützen, überprüfen Sie die Kommunikation, indem Sie die Kommunikation zwischen einem internen Benutzer in Ihrer Organisation und einem Benutzer des Skype for Business Online-Kunden testen. Wenn die Kommunikation nicht erfolgreich ist, verwenden Sie das Protokollierungstool von Ihrem Edgeserver, um Protokoll- und Ablaufverfolgungsdateien zu erfassen, um das Problem zu beheben.