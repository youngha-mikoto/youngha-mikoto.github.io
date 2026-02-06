---
layout: post
title: "[OSTEP] 36. I/O Devices"
date: 2026-02-07
categories: [ostep]
---

# CRUX: HOW TO INTEGRATE I/O INTO SYSTEMS

- How should I/O be integrated into systems?
- What are the general mechanisms?
- How can we make them efficient?

# 36.1 시스템 구조

## 일반적인 시스템의 고전적 구조

![alt text](image.png)

- CPU와 주메모리가 메모리 버스로 연결되어 있다.
- 몇 가지 장치들이 범용 I/O 버스에 연결이 되어 있는데, 많은 현대의 시스템에서는 PCI를 사용하고 있다.
- 아래에는 주변장치용 버스가 있다(SCSI, SATA, USB). 이 버스들을 통해 디스크, 마우스, 키보드와 같은 느린 장치들이 연결된다.

- 계층 구조가 필요한 이유: 물리적인 이유와 비용

  - 물리적인 이유: 버스가 고속화되려면 더 짧아져야 하는데, 그런 고속 메모리 버스에는 여러 장치들을 수용할 공간이 없다.
  - 비용: 고속의 성능을 내는 버스를 만드는 기술은 비싸다.

- 계층 구조 선택 -> 고성능 장치들을 CPU에 가깝게 배치, 느린 성능의 장치들은 멀리 배치
- 디스크처럼 느린 장치를 주변 장치 I/O 버스에 연결하여 얻는 이득: 많은 장치들을 연결할 수 있다.
