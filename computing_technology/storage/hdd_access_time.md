<!-- File: computing_technology/storage/hdd_access_time.md -->

# HDD Access Time

Hard disk access time is composed of three main components:

---

## 1. Seek Time ($T_{seek}$)

The time to move the head to the correct track or cylinder.

- Adjacent seek: movement to a neighboring cylinder.  
- Average seek: mean value across random accesses.  
- Worst-case seek: maximum head movement.

If the distance moved is $d$ cylinders and each adjacent seek costs $T_{adj}$:

$$
T_{seek}(d) \approx d \cdot T_{adj}
$$

---

## 2. Rotational Latency ($T_{rot}$)

The time for the disk to rotate so the desired sector arrives under the head.

- If disk rotates at $RPM$ revolutions per minute:

$$
T_{rotation} = \frac{60000}{RPM} \quad \text{(ms)}
$$

- Average rotational latency:

$$
T_{rot,avg} = \frac{T_{rotation}}{2}
$$

- Worst-case latency:

$$
T_{rot,max} = T_{rotation}
$$

---

## 3. Transfer Time ($T_{transfer}$)

The time to actually read or write the requested sectors.

- If reading $N$ sectors from a track with $S$ sectors:

$$
T_{transfer} = \frac{N}{S} \cdot T_{rotation}
$$

- For the entire track:

$$
T_{transfer} = T_{rotation}
$$

---

## 4. Combined Access Time

For a single random sector:

$$
T_{access} = T_{seek} + T_{rot} + T_{transfer}
$$

---

## 5. Sequential Access Rules

- Reading multiple tracks in the same cylinder:

$$
T_{cylinder} = (\text{tracks per cylinder}) \cdot T_{rotation}
$$

- Switching tracks inside a cylinder can be considered instantaneous (no seek).  

- Reading across cylinders (sequentially):

$$
T_{seq} = \sum \Big( T_{cylinder} + T_{seek,adjacent} \Big)
$$

---

# Checklist

1. Compute $T_{rotation}$ from RPM.  
2. Decide if seek is adjacent, average, or worst-case.  
3. Choose rotational latency (0, average, or max).  
4. Compute transfer time (fraction of track or whole track).  
5. For sequential access, add cylinder transfer time plus adjacent seeks.  
6. Convert from ms to seconds if needed:

$$
T_{seconds} = \frac{T_{ms}}{1000}
$$

---
