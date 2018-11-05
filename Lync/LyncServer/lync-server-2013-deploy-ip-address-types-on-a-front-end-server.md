---
title: 'Lync Server 2013: Bereitstellen von IP-Adresstypen auf einem Front-End-Server'
TOCTitle: Bereitstellen von IP-Adresstypen auf einem Front-End-Server
ms:assetid: b6c8e0f9-ec8e-4a4e-a525-756f9cd6b9d0
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205191(v=OCS.15)
ms:contentKeyID: 49295170
ms.date: 07/28/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Bereitstellen von IP-Adresstypen auf einem Front-End-Server für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-07-28_

Verwenden Sie den Topologie-Generator und führen Sie die Schritte des folgenden Verfahrens aus, um IP-Adressentypen auf einem Front-End-Server bereitzustellen.

## So stellen Sie IP-Adressentypen auf einem Front-End-Server bereit

1.  Klicken Sie unter **Enterprise Edition-Front-End-Pools** mit der rechten Maustaste auf den Server in einem Pool und wählen Sie anschließend **Eigenschaften bearbeiten** . (Wählen Sie alternativ den Server und klicken Sie auf **Eigenschaften bearbeiten** im Menü **Aktion** .)

2.  Wählen Sie im Dialogfeld **Eigenschaften bearbeiten** den IP-Adressentyp, den Sie konfigurieren möchten. Wählen Sie für Dualstapel-Konfiguration wie in der folgenden Abbildung zu sehen **IPv4 aktivieren** und **IPv6 aktivieren** .
    
    **Dialogfeld "Eigenschaften bearbeiten" für den Front-End-Server-Pool**
    
    ![Bearbeiten von Front-End-Servereigenschaften (Dialogfeld)](images/JJ205191.737a9d71-c0bc-4a54-9608-9e028dacc814(OCS.15).png "Bearbeiten von Front-End-Servereigenschaften (Dialogfeld)")
    
      - **Alle konfigurierten IP-Adressen verwenden**. Wählen Sie diese Option, wenn Sie zulassen möchten, dass eine beliebige auf dem Computer festgelegte IP-Adresse verwendet wird.
        

        > [!NOTE]
        > Diese Option wird für IP Version 6-Konfigurationen (IPv6) empfohlen.

    
      - **Dienstverwendung auf ausgewählte IP-Adressen begrenzen**. Wählen Sie diese Option, um eine spezifische Adresse zur Verwendung auf dem neuen Server anzugeben. Wenn Sie diese Option auswählen, müssen Sie einen Wert für **Primäre IP-Adresse** angeben.
    
      - **Primäre IP-Adresse**. Geben Sie eine IP-Adresse an, die der Server für sämtliche Kommunikation mit Ausnahme der PSTN (Public Switched Telephone Network, Telefonfestnetz)-Kommunikation verwendet. Die eingegebene IP-Adresse muss mit dem Format des ausgewählten Adressentyps übereinstimmen.
    
      - **PSTN-IP-Adresse**. Geben Sie eine PSTN-IP-Adresse an, wenn auf dem Front-End-Server ein Vermittlungsserver gemeinsam ausgeführt wird. Diese Adresse muss mit dem Format des ausgewählten Adressentyps übereinstimmen.

