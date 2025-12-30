# NodeScope

> Lightweight Linux node cost & health inspector  
> A single-binary CLI to answer: **“Why is this node slow right now?”**

---

## 🚨 Problem

Modern backend and AI-infra systems often fail **silently** due to:

- CPU throttling inside cgroups
- Memory reclaim & swap pressure
- Disk IO saturation
- Network retransmits & packet drops

Existing solutions are either:
- fragmented (`top`, `iostat`, `ss`)
- expensive (Datadog, New Relic)
- delayed (Prometheus dashboards)
- or unavailable on bare metal / dev nodes

Engineers need a **local, fast, offline tool** that explains *why* a node is unhealthy — not just raw metrics.

---

## 🎯 What NodeScope Does

**NodeScope** is a single static Go binary that:

- Inspects live Linux kernel metrics
- Correlates CPU, memory, disk, and network health
- Detects resource pressure & inefficiencies
- Explains *why* the node is slow
- Works on laptops, VMs, containers, and bare metal

No agents.  
No cloud dependency.  
No vendor lock-in.

---

## ✨ Key Features (v1)

### 🧠 CPU
- Load average vs available cores
- Cgroup CPU throttling & quotas
- Steal time detection

### 🧠 Memory
- RSS vs cache usage
- Swap activity & reclaim pressure
- Cgroup memory limits

### 💾 Disk
- IO wait & saturation
- Request latency
- Queue depth signals

### 🌐 Network (first-class)
- TCP retransmits
- Packet drops
- Socket state distribution (TIME_WAIT, SYN_RECV, etc.)

### 🧩 Diagnostics
- Rule-based correlation engine
- Human-readable explanations
- Machine-readable JSON output

---

## 📦 Usage

```bash
nodescope diagnose

