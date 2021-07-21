Open source body percussion. WAV files and SFZ mappings. Stereo, 44.1 kHz 24-bit files. 4-6 round robins, sometimes 2 velocity layers.

When remapping samples with 4 round robins in the quiet layer and 6 in the loud, be careful as at least some SFZ players will keep one common round robin counter for both dynamic layers. This is why those are mapped with seq_length=12 currently - as after 12 notes, both layers sync up and reach their last sample. Redoing this with separate seq_lengths for each layer can result in notes sometimes producing no sound if the internal RR counter is above 4 and a quiet sample with a seq_length of 4 has no matching seq_position. This is definitely how things work in Sforzando.

CC 0 license.