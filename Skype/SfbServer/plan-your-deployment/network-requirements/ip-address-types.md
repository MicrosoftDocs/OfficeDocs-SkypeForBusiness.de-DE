---
title: Konfigurieren von IP-Adresstypen in Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 17e756c0-6652-4cd5-b185-4b25929e3a42
description: 'Zusammenfassung: Überprüfen Sie die folgenden IP-Adresstypen, bevor Sie Skype for Business Server implementieren.'
ms.openlocfilehash: 74cb0738c7c6eb0518d8ab4ed4fae7db66921bfb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802115"
---
# <a name="configure-ip-address-types-in-skype-for-business"></a>Konfigurieren von IP-Adresstypen in Skype for Business

**Zusammenfassung:** Überprüfen Sie die folgenden IP-Adresstypen, bevor Sie Skype for Business Server implementieren.

Sie stellen IP-Adresstypen mithilfe von topologieeinstellungen bereit, die Sie im Topologie-Generator konfiguriert haben. In diesem Abschnitt wird beschrieben, wie IP-Adresstypen auf Front-End-Servern, Vermittlungsservern und Edgeserver bereitgestellt werden.

## <a name="deploy-ip-address-types-on-a-front-end-server"></a>Bereitstellen von IP-Adresstypen auf einem Front-End-Server

Führen Sie mithilfe des Topologie-Generators die Schritte im folgenden Verfahren aus, um IP-Adresstypen auf einem Front-End-Server bereitzustellen.

### <a name="to-deploy-ip-address-types-on-a-front-end-server"></a>So stellen Sie IP-Adressentypen auf einem Front-End-Server bereit

1. Klicken Sie unter **Enterprise Edition-Front-End-Pools** mit der rechten Maustaste auf den Server in einem Pool und wählen Sie anschließend **Eigenschaften bearbeiten**. (Sie können auch den Server auswählen und dann im Menü **Aktion** auf **Eigenschaften bearbeiten** klicken.)

2. Wählen Sie im Dialogfeld **Eigenschaften bearbeiten** den IP-Adressentyp, den Sie konfigurieren möchten. Wählen Sie für eine Dual-Stack-Konfiguration die Option **IPv4 aktivieren** und **IPv6 aktivieren**aus.

   **Dialogfeld „Eigenschaften bearbeiten“ für den Front-End-Server-Pool**

   - **Alle konfigurierten IP-Adressen verwenden**. Wählen Sie diese Option, wenn Sie zulassen möchten, dass eine beliebige auf dem Computer festgelegte IP-Adresse verwendet wird.

     > [!NOTE]
     > Diese Option wird für IP Version 6-Konfigurationen (IPv6) empfohlen.

   - **Dienstverwendung auf ausgewählte IP-Adressen begrenzen**. Wählen Sie diese Option, um eine spezifische Adresse zur Verwendung auf dem neuen Server anzugeben. Wenn Sie diese Option auswählen, müssen Sie einen Wert für **Primäre IP-Adresse** angeben.

   - **Primäre IP-Adresse**. Geben Sie eine IP-Adresse an, die der Server für sämtliche Kommunikationsvorgänge mit Ausnahme der PSTN (Public Switched Telephone Network, Telefonfestnetz)-Kommunikation verwendet. Die eingegebene IP-Adresse muss mit dem Format des ausgewählten Adressentyps übereinstimmen.

   - **PSTN-IP-Adresse**. Geben Sie eine PSTN-IP-Adresse an, wenn auf dem Front-End-Server ein Vermittlungsserver angeordnet wird. Diese Adresse muss mit dem Format des ausgewählten Adressentyps übereinstimmen.

> [!NOTE]
> Die Installation zusätzlicher Netzwerkschnittstellenkarten (NICs) zur Unterstützung der Konfiguration der PSTN-IP-Adresse (oder aus anderen Gründen) auf Front-End-Servern wird nicht unterstützt. Weitere Informationen zu unterstützten NIC-Konfigurationen für Skype for Business Server finden Sie unter [Server-Hardwareplattformen für lync Server 2013](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).

## <a name="deploy-ip-address-types-on-a-mediation-server"></a>Bereitstellen von IP-Adresstypen auf einem Vermittlungsserver

Führen Sie mithilfe des Topologie-Generators die Schritte im folgenden Verfahren aus, um IP-Adresstypen auf einem Vermittlungs Server bereitzustellen.

### <a name="to-deploy-ip-address-types-on-a-mediation-server"></a>So stellen Sie IP-Adresstypen auf einem Vermittlungsserver bereit

- Klicken Sie im Topologie-Generator unter **Vermittlungs Pools**mit der rechten Maustaste auf den Server in einem Pool, und wählen Sie dann **Eigenschaften bearbeiten**aus. (Sie können auch den Server auswählen und dann im Menü **Aktion** auf **Eigenschaften bearbeiten** klicken.)

- Wählen Sie im Dialogfeld **Eigenschaften bearbeiten** den IP-Adressentyp, den Sie konfigurieren möchten. Wählen Sie für eine Dualstapel-Konfiguration wie in der folgenden Abbildung zu sehen **IPv4 aktivieren** und **IPv6 aktivieren**.

   **Das Dialogfeld „Eigenschaften bearbeiten“ für den Vermittlungsserverpool**

  - **Alle konfigurierten IP-Adressen verwenden**. Wählen Sie diese Option, wenn Sie zulassen möchten, dass eine beliebige auf dem Computer festgelegte IP-Adresse verwendet wird.

    > [!NOTE]
    > Diese Option wird für IP Version 6-Konfigurationen (IPv6) empfohlen.

  - **Dienstverwendung auf ausgewählte IP-Adressen begrenzen**. Wählen Sie diese Option, um eine spezifische Adresse zur Verwendung auf dem neuen Server anzugeben. Wenn Sie diese Option auswählen, müssen Sie einen Wert für „Primäre IP-Adresse“ angeben.

  - **Primäre IP-Adresse**. Geben Sie eine IP-Adresse an, die der Server für sämtliche Kommunikationsvorgänge mit Ausnahme der PSTN (Public Switched Telephone Network, Telefonfestnetz)-Kommunikation verwendet. Die eingegebene IP-Adresse muss mit dem Format des ausgewählten Adressentyps übereinstimmen.

  - **PSTN-IP-Adresse**. Geben Sie eine PSTN-IP-Adresse an, wenn auf dem Front-End-Server ein Vermittlungsserver angeordnet wird. Diese Adresse muss mit dem Format des ausgewählten Adressentyps übereinstimmen.
> [!IMPORTANT]
> Wir unterstützen nur zwei Netzwerkkarten auf *dedizierten* Vermittlungsservern. Wenn die Rolle der Mediations-sServer auf der Vorderseite liegt, werden keine dualen Netzwerkkarten unterstützt. 

> [!NOTE]
> - Weitere Informationen zu unterstützten NIC-Konfigurationen für Skype for Business Server 2015 finden Sie unter [Hardware für Skype for Business Server 2015](../requirements-for-your-environment/server-requirements.md#hardware-for-skype-for-business-server-2015)
> - Weitere Informationen zu unterstützten NIC-Konfigurationen für Skype for Business Server 2019 finden Sie unter [Hardware für Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md#hardware-for-skype-for-business-server-2019)



## <a name="deploy-ip-address-types-on-an-edge-server"></a>Bereitstellen von IP-Adresstypen auf einem Edgeserver

Führen Sie mithilfe des Topologie-Generators die folgenden Schritte aus:

### <a name="to-deploy-ip-address-types-on-an-edge-server"></a>So stellen Sie IP-Adresstypen auf dem Edgeserver bereit

1. Klicken Sie im Topologie-Generator unter **Edge-Pools**mit der rechten Maustaste auf den Server in einem Pool, und wählen Sie dann **Eigenschaften bearbeiten**aus. (Sie können auch den Server auswählen und dann im Menü **Aktion** auf **Eigenschaften bearbeiten** klicken.)

2. Wählen Sie im Fenster **Eigenschaften bearbeiten** die IP-Adresskonfiguration, die Sie unterstützen möchten.

3. Für jeden Adresstyp, den Sie auswählen, müssen Sie die geeigneten internen und externen Adressen auswählen.
