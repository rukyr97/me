# Initial Thoughts on FA Adaptation Challenges

Frame aggregation increases the throughput in the MAC-layer and it was introduced in 802.11n.
It reduces the overhead of inter-frame spacing, acknowledgments (ACK) and headers.
With the aggregation of multiple MPDUs into one large Aggregated MPDU (A-MPDU).

However there are tradeoffs:

* Small number of aggregated MPDUs result in lower throughput but lower Frame Error Rate (FER)
* Higher number of aggregated MPDUs has higher error rate (may result in lower throughput)

What affects the MPDU delivery ratio (MDR):

* Chosen **Modulation and Coding Scheme** (MCS) - Transmission rate
* **Speed of Movement**

These change throughout the time, therefore adaptation of size of A-MPDU is required. 
The challenges in frame aggregation adaptation: 

* **Channel compensation limitations** - FER of MPDUs depend on its location in an A-MPDU (the farther away from the preamble, the higher the FER)
* **Dependencies between A-MPDUS** - Block ACK *start sequence number* and *64-bit bitmap* affect the fate of future A-MPDUs (see [1] sec2.2)

Source Article:

[1] https://doi.org/10.1016/j.comcom.2021.09.019

    #PhD #Frame_Aggregation #Link_Adaptation
