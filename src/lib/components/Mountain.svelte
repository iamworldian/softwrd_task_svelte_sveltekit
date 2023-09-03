<div class="outer-square">
    <div class="inner-circle"></div>
</div>


<style>
    .outer-square{
        height: 300px;
        width: 300px;
        background-color: #293462;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;

    }

    .inner-circle{
        height: 200px;
        width: 200px;
        background-color: #fdfc9a;
        border-radius: 50%;
        position: relative;
        overflow: hidden;
        transform: rotate(45deg);
    }

    .inner-circle:before,
                 :after{
            content: '';
            position: absolute;
            background-color: #fe5f55;
    }

    .inner-circle:before{
        width: 30px;
        height: 30px;
        right: calc(50% - 1px);
        bottom: 0;
    }

    .inner-circle:after{
        width: 50%;
        height: 100%;
        left: 50%;
        top: 40px;
    }
</style>