<script>
    import { Modal, Content, Trigger } from "sv-popup";
</script>
<Modal>
    <Content>
        <iframe
        src="https://www.youtube.com/embed/S_CGed6E610"
        title="YouTube video player"
        frameborder="0"
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
        allowfullscreen
        style="width: 100%;aspect-ratio: 16/9;height: auto;"
        />
    </Content>
    <Trigger>
        <slot />
    </Trigger>
</Modal>