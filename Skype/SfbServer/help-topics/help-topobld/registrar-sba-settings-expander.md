---
title: SBA-Einstellungen der Registrierungsstelle – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.RegistrarSBASettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 68ea1fc0-9cd1-4e0a-995e-b53845493477
description: 'Sie bearbeiten die Einstellungen für Flexibilität und konfigurieren die folgenden Eigenschaften:'
ms.openlocfilehash: 6424b43ea7c56760bb8d58ee35d9804c49c435dd
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217216"
---
# <a name="registrar-sba-settings-expander"></a><span data-ttu-id="91aa2-103">SBA-Einstellungen der Registrierungsstelle – Erweiterung</span><span class="sxs-lookup"><span data-stu-id="91aa2-103">Registrar SBA Settings Expander</span></span>

<span data-ttu-id="91aa2-104">Sie bearbeiten die Einstellungen für **Flexibilität** und konfigurieren die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="91aa2-104">You edit the settings for **Resiliency** and configure the following properties:</span></span>

- <span data-ttu-id="91aa2-105">Wählen Sie in der Liste die Option **Zugeordneter Benutzerdienst und Sicherungsregistrierungsstellen-Pool** aus.</span><span class="sxs-lookup"><span data-stu-id="91aa2-105">Select **Associated User service and backup Registrar pool** from the list.</span></span>

    <span data-ttu-id="91aa2-106">Aktivieren Sie optional das Kontrollkästchen **Automatisches Failover und Failback für Sprachdienste**.</span><span class="sxs-lookup"><span data-stu-id="91aa2-106">Optionally, select the **Automatic failover and failback for Voice** check box.</span></span>

    <span data-ttu-id="91aa2-p101">Konfigurieren Sie die Optionen **Erkennungsintervall für Sprachdienstfehler (Sek.)** und **Failbackintervall für Sprache (Sek.)**. Die Standardeinstellungen für die Intervalle lauten 120 Sekunden für die Erkennung von Sprachdienstfehlern und 240 Sekunden für das Failback für Sprache.</span><span class="sxs-lookup"><span data-stu-id="91aa2-p101">Configure the **Voice failure detection interval (sec)** and the **Voice failback interval (sec)**. By default, the intervals are 120 seconds for Voice failure detection and 240 seconds for Voice failback.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="91aa2-p102">Die Anzahl an Sekunden, die Sie für Failover- und Failbackintervalle definieren, muss sorgfältig getestet werden, um sicherzustellen, dass die Ausfallsicherheit wie gewünscht funktioniert. Wenn das Intervall zu kurz ist (weniger als 120 Sekunden) oder Failover und Failback zu eng festgelegt sind, kann dies dazu führen, dass Failover und Failback nicht wie gewünscht funktionieren.</span><span class="sxs-lookup"><span data-stu-id="91aa2-p102">The number of seconds that you define for the failover and failback intervals should be carefully tested to ensure that the resiliency works as expected. Setting the interval to low (that is, less than 120 seconds) or the failover and failback set too closely may result in the actual failover and failback not working as expected.</span></span>

  <span data-ttu-id="91aa2-111">**OK**: Mit dieser Option werden die Änderungen am Dialogfeld akzeptiert und übernommen.</span><span class="sxs-lookup"><span data-stu-id="91aa2-111">**OK** Accepts and commits changes to the dialog.</span></span>

  <span data-ttu-id="91aa2-112">**Abbrechen**: Mit dieser Option werden die Änderungen verworfen, und das Dialogfeld wird geschlossen.</span><span class="sxs-lookup"><span data-stu-id="91aa2-112">**Cancel** Discards changes and closes the dialog.</span></span>

  <span data-ttu-id="91aa2-113">**Hilfe**: Mit dieser Option zeigen Sie diese Hilfeseite an.</span><span class="sxs-lookup"><span data-stu-id="91aa2-113">**Help** Displays this help screen.</span></span>

## <a name="see-also"></a><span data-ttu-id="91aa2-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="91aa2-114">See also</span></span>

[<span data-ttu-id="91aa2-115">Planung für die Ausfallsicherheit von Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="91aa2-115">Planning for Enterprise Voice Resiliency</span></span>](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)
