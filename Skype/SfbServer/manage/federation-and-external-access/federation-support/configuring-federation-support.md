---
title: Konfigurieren der Verbundunterstützung für einen Skype for Business Online Kunden
ms.reviewer: ''
ms:assetid: e5f7f38d-ede5-4af3-88c2-026e8a78df12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202193(v=OCS.15)
ms:contentKeyID: 48185669
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Wenn Sie Skype for Business in Ihrer Organisation bereitstellen, können Sie einen Verbund mit den Domänen eines oder mehrerer Skype for Business Online-Kunden durchsetzen. '
ms.openlocfilehash: b7488d21463782a978c9a3d6263d9fdfc2e59dd9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037285"
---
# <a name="configuring-federation-support-for-a-skype-for-business-online-customer-in-skype-for-business-server"></a>Konfigurieren der Verbundunterstützung für einen Skype for Business Online Kunden in Skype for Business Server 

Sie können Benutzern in Ihrer Organisation auf die folgende Art Kommunikationsdienste bieten:

  - Bereitstellen von Skype for Business Server in Ihrer Organisation (als *Lokale Dienste*bezeichnet) und Einrichten von Skype for Business Benutzerkonten in Ihrer Organisation.
  - Einrichten eines Microsoft Skype for Business Online-Kundenkontos bei einem Hostinganbieter und Einrichten von Benutzerkonten beim Hosting-Anbieter (als *Online Dienste*bezeichnet).

Wenn Sie Skype for Business in Ihrer Organisation bereitstellen, können Sie einen Verbund mit den Domänen eines oder mehrerer Skype for Business Online-Kunden durchsetzen. Um den Partnerverbund zwischen Benutzern Ihrer lokalen Skype for Business-Bereitstellung und Benutzern eines Skype for Business Online-Kunden zu aktivieren, müssen Sie die Unterstützung für die Domäne und die Benutzer des Skype for Business Online-Kunden konfigurieren.

> [!NOTE]  
> In dieser Dokumentation werden nur die Verfahren zum Konfigurieren Ihrer Organisation zur Unterstützung des Verbunds mit einem Skype for Business Online Kunden beschrieben. In dieser Dokumentation werden die Verfahren zum Konfigurieren des Skype for Business Online Kunden zur Unterstützung des Verbunds nicht beschrieben. 

## <a name="prerequisites-for-federating-with-a-skype-for-business-online-customer"></a>Voraussetzungen für die verbundierung mit einem Skype for Business Online-Kunden

Damit Sie einen Verbund mit einem Skype for Business Online-Kunden abschließen können, sollten Sie die anfängliche Bereitstellung und Konfiguration von Skype for Business Server in Ihrer Organisation bereits abgeschlossen haben. Dazu gehört Folgendes:

  - Bereitstellen von mindestens einem Standard Edition-Server oder einem Enterprise Edition-Front-End-Pool in Ihrer Organisation. 
  - Aktivieren interner Benutzerkonten für Skype for Business Server. 
  - Bereitstellen von mindestens einem Edgeserver und den anderen Komponenten, die zur Unterstützung des Zugriffs durch externe Benutzer erforderlich sind Ausführliche Informationen finden Sie unter [Managing Federation und External Access to Skype for Business Server](../managing-federation-and-external-access.md).
  - Aktivieren der Verbundunterstützung in Ihrer Organisation und Konfigurieren der geeigneten Methode für die Steuerung des Zugriffs durch Verbunddomänen. Ausführliche Informationen finden Sie unter [Aktivieren oder Deaktivieren des Remotebenutzerzugriffs](../access-edge/enable-or-disable-remote-user-access.md) und [Verwalten von SIP-Verbund Anbietern für Ihre Organisation](../sip-providers/manage-sip-federated-providers-for-your-organization.md).
  - Aktivieren des Zugriffs externer Benutzer für Benutzer in Ihrer Organisation. Ausführliche Informationen finden Sie unter [Zuweisen einer Richtlinie für den externen Benutzer Zugriff auf einen Skype for Business aktivierten Benutzer](../external-access-policies/assign-an-external-user-access-policy.md).



## <a name="configure-federation-support-for-a-skype-for-business-online-domain"></a>Konfigurieren der Verbundunterstützung für eine Skype for Business Online Domäne

Für die Zusammensetzung mit einem Skype for Business Online-Kunden müssen Sie die folgenden Schritte ausführen:

  - Konfigurieren Sie die Unterstützung für die Domäne des Skype for Business Online 2010-Kunden (beispielsweise contoso.onmicrosoft.com). Wie unter [Voraussetzungen für die Zusammenarbeit mit einem Skype for Business Online-Kunden](#prerequisites-for-federating-with-a-skype-for-business-online-customer)angegeben, sollten Sie den Partnerverbund für Ihre Organisation bereits aktiviert haben. Zum Aktivieren des Partnerverbunds muss die Methode zur Steuerung des Zugriffs durch Partnerdomänen angegeben werden. Wenn in Ihrer Organisation die Ermittlung verwendet wird, kann die Domäne optional der Liste der zugelassenen Domänen Ihrer Organisation hinzugefügt werden. Wenn Sie die Domänen Ermittlung nicht aktiviert haben, müssen Sie den Domänennamen des Skype for Business Online Kunden der Liste der zugelassenen Domänen hinzufügen. Sie können einen Domänennamen entweder über Skype for Business Server Systemsteuerung oder durch Ausführen des Cmdlets **New-CSAllowedDomain** hinzufügen. Ausführliche Informationen zur Verwendung Skype for Business Server-Systemsteuerung, einschließlich der Aktivierung der Suche von Domänen, finden Sie unter [Manage SIP Federated Providers for your organization in Skype for Business Server](../sip-providers/manage-sip-federated-providers-for-your-organization.md). Ausführliche Informationen zur Verwendung des **New-CSAllowedDomain-** Cmdlets zum Hinzufügen einer Domäne finden Sie unter [New-CSAllowedDomain](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain).

    > [!NOTE]  
    > Ein Skype for Business Online Kunde kann mehrere Domänen haben. Wenn Sie eine Föderation mit mehr als einer der Domänen durchsetzen möchten, müssen Sie die Unterstützung für jede einzelne Domäne konfigurieren, für die Sie den Verbund unterstützen möchten, und der Administrator des Skype for Business Online Kunden muss den Partnerverbund für jede der Domänen aktivieren, um Verbund sein.

  - Konfigurieren Sie die Unterstützung für den Hostinganbieter der Skype for Business Online Kundendomäne, mit der Sie einen Partnerverbund einrichten möchten. Verwenden Sie das Verfahren in diesem Abschnitt, um die Unterstützung für Hostinganbieter zu konfigurieren.

    > [!NOTE]  
    > Dieser Schritt ist nur für den Verbund mit einer Domäne eines Skype for Business Online Kunden erforderlich, nicht für den Verbund mit einer Domäne, die lokal am Standort des Verbundpartners bereitgestellt wird.


### <a name="to-configure-support-for-a-hosting-provider"></a>So konfigurieren Sie die Unterstützung für einen Hostinganbieter

1.  Starten Sie in einer Front-End-Server die Skype for Business Server Verwaltungsshell: Klicken Sie auf **Start**, auf **Alle Programme**, klicken Sie auf **Skype for Business Server**, und klicken Sie dann auf **Skype for Business Server Verwaltungsshell**.

2.  Führen Sie das Cmdlet **New-CsHostingProvider** aus, um den Hostinganbieter zu erstellen und zu konfigurieren. Führen Sie beispielsweise den folgenden Befehl aus:
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    Im oben stehenden Beispiel werden folgende Parameter festgelegt:
    
      - **Identity** gibt einen eindeutigen Zeichenfolgenwert für den Hostinganbieter an, den Sie erstellen. Beachten Sie, dass der Befehl nicht erfolgreich ist, wenn bereits ein Anbieter mit dieser Identität konfiguriert wurde.
    
      - **ProxyFQDN** gibt den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des vom Hostinganbieter verwendeten Proxyservers an. Dieser Wert kann nicht geändert werden. Wenn der Hostinganbieter seinen Proxyserver ändert, muss der Eintrag für diesen Anbieter gelöscht und neu erstellt werden.
    
      - **VerificationLevel** gibt an, wie (oder ob) von einem Hostinganbieter gesendete Nachrichten überprüft werden, um sicherzustellen, dass sie tatsächlich von diesem Anbieter stammen.
    
      - **Enabled** gibt an, ob die Netzwerkverbindung zwischen Ihrer Domäne und dem Hostinganbieter aktiviert ist. Der Nachrichtenaustausch zwischen zwei Organisationen ist erst möglich, wenn dieser Wert auf **True** festgelegt ist.
    
      - **EnabledSharedAddressSpace** gibt an, ob der Hostinganbieter in einem Szenario mit freigegebenem SIP-Adressraum (getrennte Domäne) verwendet wird.
    
      - **HostsOCSUsers** gibt an, ob der Hostinganbieter zum Hosten von Skype for Business Server Konten verwendet wird. Der Wert **False** gibt an, dass der Anbieter andere Kontotypen (z. B. Microsoft Exchange-Konten) hostet.
    
      - **IsLocal** gibt an, ob der vom Hostinganbieter verwendete Proxy Server in Ihrer Skype for Business Server Topologie enthalten ist.
    
    Ausführliche Informationen zur Verwendung dieses Cmdlets finden Sie unter [New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider).

## <a name="configure-user-access-for-federation-with-a-skype-for-business-online-customer"></a>Konfigurieren des Benutzerzugriffs für einen Partnerverbund mit einem Skype for Business Online Kunden 

Sie müssen die Benutzerkonten aller Benutzer in der Organisation so konfigurieren, dass die Kommunikation mit Verbundpartnern zulässig ist. Diese Konfiguration wird für alle Verbundpartner, einschließlich aller Microsoft Skype for Business Online-Kunden Domänen, mit denen Sie den Verbund unterstützen, angewendet. Ausführliche Informationen zum Konfigurieren der Verbundunterstützung für Benutzerkonten finden Sie unter [configure Policies to Control Partner User Access](../external-access-policies/configure-policies-to-control-federated-user-access.md) und [Zuweisen einer Richtlinie für den externen Benutzer Zugriff auf einen Skype for Business aktivierten Benutzer](../external-access-policies/assign-an-external-user-access-policy.md).

## <a name="verify-communications-with-a-skype-for-business-online-customer-in-skype-for-business-server"></a>Überprüfen der Kommunikation mit einem Skype for Business Online Kunden in Skype for Business Server

Damit Skype for Business Benutzer in Ihrer Organisation mit Benutzern eines Skype for Business Online-Kunden kommunizieren können, müssen Sie die folgenden Schritte ausgeführt haben:

  - Erfüllt alle Voraussetzungen. Dies umfasst die Bereitstellung Ihrer internen und Edgeserver, die Aktivierung der Verbundunterstützung für Ihre Organisation und das Einrichten von Benutzerkonten. Ausführliche Informationen finden Sie unter [Voraussetzungen für die verbundierung mit einem Skype for Business Online Kunden](#prerequisites-for-federating-with-a-skype-for-business-online-customer).
  - Konfigurierte Domänenzugriffs Unterstützung in ihrer internen Bereitstellung. Dies umfasst das Erstellen eines Eintrags eines Host Anbieters und das Konfigurieren Ihrer Bereitstellung, um den Zugriff aus der Domäne des Skype for Business Online Kunden zuzulassen. Ausführliche Informationen finden Sie unter [Konfigurieren der Verbundunterstützung für eine Skype for Business Online Domäne](#configure-federation-support-for-a-skype-for-business-online-domain).
  - Konfigurieren Sie Ihre Benutzerkonten für die Unterstützung des Verbunds. Ausführliche Informationen finden Sie unter [Konfigurieren des Benutzerzugriffs für einen Partnerverbund mit einem Skype for Business Online-Kunden](#configure-user-access-for-federation-with-a-skype-for-business-online-customer).

Nachdem Sie alle diese Schritte ausgeführt haben und der Administrator des Skype for Business Online Kunden die gesamte Konfiguration seiner Online Dienste abgeschlossen hat, um den Verbund mit Ihrer Organisation zu unterstützen, überprüfen Sie die Kommunikation durch Testen der Kommunikation zwischen einem interner Benutzer in Ihrer Organisation und ein Benutzer des Skype for Business Online Kunden. Wenn die Kommunikation nicht erfolgreich ist, verwenden Sie das Protokollierungs Tool aus dem Edgeserver, um Protokoll-und Ablaufverfolgungsdateien aufzuzeichnen, um das Problem zu beheben. 
