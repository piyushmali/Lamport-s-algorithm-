# Lamport-s-algorithm-

Lamport’s algorithm remedies the situation by forcing a resequencing of timestamps to ensure that the happens before relationship is properly depicted for events related to sending and receiving messages. It works as follows:

Each process has a clock, which can be a simple counter that is incremented for each event.

The sending of a message is an event and each message carries with it a timestamp obtained from the current value of the clock at that process (sequence number).

The arrival of a message at a process is also an event will also receive a timestamp – by the receiving process, of course. The process’ clock is incremented prior to timestamping the event, as it would be for any other event. If the clock value is less than the timestamp in the received message, the system’s clock is adjusted to the (message’s timestamp + 1). Otherwise nothing is done. The event is now timestamped.

Lamport's algorithm allows us to maintain proper time ordering among causally-related events. In summary, Lamport’s algorithm requires a monotonically increasing software counter for a “clock” that has to be incremented at least when events that need to be timestamped take place. These events will have the clock value, or “Lamport timestamp,” associated with them.

Lamport timestamps assure us that if there is a causal relationship between two events, then the earlier event will have a smaller time- stamp than the later event. Causality is achieved by successive events on one process or by the sending and receipt of messages on different processes. As defined by the happened-before relationship, causality is transitive.
