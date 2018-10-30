---
title: 'Lync Server 2013: Bereitstellen von IP-Adresstypen auf einem Vermittlungsserver'
TOCTitle: Bereitstellen von IP-Adresstypen auf einem Vermittlungsserver
ms:assetid: 689ebed5-96ee-4cd4-b7ae-ee2a86a1d9b3
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204964(v=OCS.15)
ms:contentKeyID: 49294275
ms.date: 07/20/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Bereitstellen von IP-Adresstypen auf einem Vermittlungsserver für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-07-28_

Verwenden Sie den Topologie-Generator und führen Sie die Schritte des folgenden Verfahrens aus, um IP-Adressentypen auf einem Vermittlungsserver bereitzustellen.

## So stellen Sie IP-Adresstypen auf einem Vermittlungsserver bereit

  - Klicken Sie im Topologie-Generator unter **Vermittlungspools** mit der rechten Maustaste auf den in einem Pool befindlichen Server und wählen Sie dann **Eigenschaften bearbeiten** aus. (Alternativ dazu können Sie auch den Server auswählen und dann auf **Eigenschaften bearbeiten** im Menü **Aktion** klicken.)

  - Wählen Sie im Dialogfeld **Eigenschaften bearbeiten** den IP-Adressentyp, den Sie konfigurieren möchten. Wählen Sie für Dualstapel-Konfiguration wie in der folgenden Abbildung zu sehen **IPv4 aktivieren** und **IPv6 aktivieren**.
    
    **Das Dialogfeld "Eigenschaften bearbeiten" für den Vermittlungsserverpool**
    
    ![Allgemeine Lync Server-Eigenschaften mit FQDN (Seite)](images/JJ204964.4e650aca-dbff-4a86-b10d-f0162c032539(OCS.15).png "Allgemeine Lync Server-Eigenschaften mit FQDN (Seite)")
    
      - **Alle konfigurierten IP-Adressen verwenden**. Wählen Sie diese Option, wenn Sie zulassen möchten, dass eine beliebige auf dem Computer festgelegte IP-Adresse verwendet wird.
        

        > [!NOTE]
        > Diese Option wird für IP Version 6-Konfigurationen (IPv6) empfohlen.

    
      - **Dienstnutzung auf ausgewählte IP-Adressen beschränken**. Aktivieren Sie diese Option, um eine bestimmte IP-Adresse anzugeben, die auf dem neuen Server verwendet werden soll. Bei Auswahl dieser Option müssen Sie einen Wert für die "Primäre IP-Adresse" angeben.
    
      - **Primäre IP-Adresse**. Geben Sie eine IP-Adresse an, die der Server für sämtliche Kommunikation mit Ausnahme der PSTN (Public Switched Telephone Network, Telefonfestnetz)-Kommunikation verwendet. Die eingegebene IP-Adresse muss mit dem Format des ausgewählten Adressentyps übereinstimmen.
    
      - **PSTN-IP-Adresse**. Geben Sie eine PSTN-IP-Adresse an, wenn auf dem Front-End-Server ein Vermittlungsserver gemeinsam ausgeführt wird. Diese Adresse muss mit dem Format des ausgewählten Adressentyps übereinstimmen.
        

        > [!NOTE]
        > Die Installation zusätzlicher Netzwerkschnittstellenkarten (NICs) zur Unterstützung der IP-Adresskonfiguration des PSTN für Lync Server 2013 wird nicht unterstützt. Weitere Informationen zu unterstützten NIC-Konfigurationen für Lync Server 2013 finden Sie unter <A href="lync-server-2013-server-hardware-platforms.md">Serverhardwareplattformen für Lync Server&nbsp;2013</A>.


