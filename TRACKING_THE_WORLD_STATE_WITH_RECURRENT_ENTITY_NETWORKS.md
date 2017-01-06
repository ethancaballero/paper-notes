There's a bunch of memory slots that each can be used to represent a single entity. The first time an entity appears, it's written to a slot. Every time that something happens in the story that corresponds to a change in the state of an entity, the change in the state of that entity is combined with the entity's previous state via a modified gru update equation and rewritten to the same slot.

During Decode, it uses standard attention to read from these entity slots based on a question or decode_context.

Why did they only test for single hop? Is it because of scaling issues? If so, you need to add sparse read write from https://arxiv.org/abs/1610.09027

EntNet can be considered as another form of Active Memory (https://arxiv.org/abs/1610.08613).
